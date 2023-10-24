<script>
    // We'll manage the form's submitted state to give feedback to the user.
    let wasSubmitted = false;

    // Function to handle the form's submitted state
    function handleSuccess() {
        wasSubmitted = true;
    }
</script>

<div>
    {#if wasSubmitted}
        <p>Thank you! Your message has been sent.</p>
    {:else}
        <h2>Contact Us</h2>
        <!-- The form now points to Formspree's endpoint -->
        <form action="https://formspree.io/f/mvojlqly" method="POST" on:submit|preventDefault={handleSuccess}>
            <!-- Your form fields here -->
            <div>
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" required />
            </div>

            <div>
                <label for="email">Email:</label>
                <input type="email" id="email" name="_replyto" required />
            </div>

            <div>
                <label for="message">Message:</label>
                <textarea id="message" name="message" required></textarea>
            </div>

            <!-- The submit button for the form -->
            <button type="submit">Send</button>
        </form>
    {/if}
</div>
