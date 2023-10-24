<script>
    // You can import and use image assets, links for social media, etc.
    import logo from './logo.png'; // Update with your logo's path
</script>

<style>
    .footer {
        display: flex;
        justify-content: space-between; /* Distributes the space between items */
        align-items: center;
        padding: 20px 10px;
        background-color: #333; /* Dark background */
        color: white; /* Light text */
        font-size: 14px; /* Adjust as needed */
    }

    .footer-logo {
        width: 100px; /* Adjust as needed */
    }

    .footer-menu {
        text-align: center;
    }

    .footer-menu ul {
        list-style: none;
        padding: 0;
    }

    .footer-menu li {
        display: inline; /* Or 'inline-block' for a bit of spacing */
        margin: 0 10px; /* Space out the menu items */
    }

    .social-media {
        text-align: right;
    }

    .social-media ul {
        list-style: none;
        padding: 0;
    }

    .social-media li {
        display: inline; /* Or 'inline-block' for a bit of spacing */
        margin: 0 10px; /* Space between icons */
    }

    /* Adjustments for smaller screens */
    @media (max-width: 768px) {
        .footer {
            flex-direction: column;
            align-items: start;
        }

        .footer-menu, .social-media {
            text-align: left;
        }
    }
</style>

<footer class="footer">
    <!-- Logo on the left -->
    <div class="footer-logo">
        <img src={logo} alt="logo" />
    </div>

    <!-- Menu in the center with text underneath -->
    <div class="footer-menu">
        <ul>
            <li>Home</li>
            <li>About</li>
            <li>Services</li>
            <li>Contact</li>
        </ul>
        <p>Some text underneath the menu</p>
    </div>

    <!-- Social media links on the right with text underneath -->
    <div class="social-media">
        <ul>
            <li><a href="https://www.facebook.com/yourpage" target="_blank">Facebook</a></li>
            <li><a href="https://www.twitter.com/yourprofile" target="_blank">Twitter</a></li>
            <li><a href="https://www.linkedin.com/in/yourprofile" target="_blank">LinkedIn</a></li>
        </ul>
        <p>Connect with us on social media</p>
    </div>
</footer>
