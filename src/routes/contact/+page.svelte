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
<style>
    /* General styles, consider setting these in your global stylesheet */
    body, html {
        height: 100%;
        margin: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        background: #f7f7f7; /* or any other background you prefer */
        font-family: Arial, sans-serif; /* or any other font you prefer */
    }

    /* Styles for the form container */
    .form-holder {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh; /* Full viewport height */
        width: 100%;
        padding: 15px; /* Prevents the form from touching the viewport edges */
        box-sizing: border-box;
    }
    .msg{
    height: 10rem;
    }

    /* Styles for the form container */
    .form-container {
        background: #ffffff;
        border-radius: 10px; /* This gives the rounded corners */
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        padding: 20px;
        max-width: 1000px;
        max-height: 1000px;
        width: 100%;
        box-sizing: border-box;
        height: 100%;
    }

    /* Styles for the form elements */
    input, textarea, button {
        width: calc(100% - 20px);
        padding: 10px;
        margin-bottom: 20px; /* Spacing between form fields */
        border: 1px solid #ccc;
        border-radius: 5px; /* Slightly rounded corners on inputs */
    }

    textarea {
        resize: vertical; /* Allow vertical resizing */
    }

    button {
        background: #007bff; /* Arbitrary color, change to match your design */
        color: white;
        border: none;
        cursor: pointer;
        transition: background 0.3s ease;
    }

    button:hover {
        background: #0056b3; /* Darken the button color on hover */
    }

    button:disabled {
        background: #ccc;
        cursor: not-allowed;
    }

    /* Media query for small screens (e.g., phones) */
    @media (max-width: 600px) {
        .form-container {
            box-shadow: none;
            margin: 0;
        }
    }
</style>
<div class="form-holder">
<div class="form-container">
    <h2>Contact Us</h2>
    {#if formState === 'success'}
        <p>Thank you! Your message has been sent.</p>
    {:else}
        <form on:submit|preventDefault={handleSubmit}>
            <label>
                Your email:
                <input class="email" type="email" bind:value={email} name="email" required>
            </label>
            <label>
                Your message:
                <textarea class="msg" bind:value={message} name="message" required></textarea>
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
</div>
