<script>
    let name = '';
    let email = '';
    let message = '';

    function handleSubmit() {
        // Here, you'd typically make a POST request to your server with the form data.
        // For this example, we'll just log the input to the console.
        console.log({name, email, message});

        // Clear the form fields after submission
        name = '';
        email = '';
        message = '';
    }
</script>

<style>
    /* Add styles for your form elements here */
</style>

<div>
    <h2>Contact Us</h2>
    <form on:submit|preventDefault={handleSubmit}>
        <div>
            <label for="name">Name:</label>
            <input type="text" id="name" bind:value={name} required />
        </div>

        <div>
            <label for="email">Email:</label>
            <input type="email" id="email" bind:value={email} required />
        </div>

        <div>
            <label for="message">Message:</label>
            <textarea id="message" bind:value={message} required></textarea>
        </div>

        <div>
            <button type="submit">Send</button>
        </div>
    </form>
</div>
