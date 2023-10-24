<script>
    let email = '';
    let message = '';
    let formState = ''; // Keeps track of the form's state ("" | "loading" | "success" | "error")

    async function handleSubmit(event) {
        event.preventDefault(); // Prevents the default form submission behaviour
        formState = 'loading';

        const formData = new FormData();
        formData.append('email', email);
        formData.append('message', message);

        try {
            const response = await fetch('https://formspree.io/f/mvojlqly', {
                method: 'POST',
                body: formData,
                headers: {
                    'Accept': 'application/json' // This is to expect a JSON response
                }
            });

            if (response.ok) {
                // If the submission was successful, reset the form and set the state to 'success'
                email = '';
                message = '';
                formState = 'success';
            } else {
                // If there was an error with the submission, set the state to 'error'
                formState = 'error';
            }
        } catch (error) {
            // In case of a network error or other issues, set the state to 'error'
            formState = 'error';
            console.error('Error submitting form', error);
        }
    }
</script>

<div>
    <h2>Contact Us</h2>
    {#if formState === 'success'}
        <p>Thank you! Your message has been sent.</p>
    {:else}
        <form on:submit|preventDefault={handleSubmit}>
            <label>
                Your email:
                <input type="email" bind:value={email} name="email" required>
            </label>
            <label>
                Your message:
                <textarea bind:value={message} name="message" required></textarea>
            </label>
            {#if formState === 'loading'}
                <button type="submit" disabled>Sending...</button>
            {:else}
                <button type="submit">Send</button>
            {/if}
        </form>
        {#if formState === 'error'}
            <p>There was an error sending your message. Please try again.</p>
        {/if}
    {/if}
</div>
