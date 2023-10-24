<script>
</script>

<style>
    .footer {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 20px 10px;
        background-color: #333;
        color: white;
    }

    .footer-logo img {
        width: 50px; /* Adjust based on your preference */
        height: auto;
    }

    .footer-menu {
        text-align: center;
    }

    .footer-menu ul {
        list-style: none;
        padding: 0;
    }

    .footer-menu li {
        display: inline;
        margin: 0 10px;
    }

    .social-media {
        text-align: right;
    }

    .social-media ul {
        list-style: none;
        padding: 0;
    }

    .social-media li {
        display: inline;
        margin: 0 10px;
    }

    .social-icon {
        width: 20px; /* Adjust based on your preference */
        height: 20px;
        vertical-align: middle;
    }

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
    <div class="footer-logo">
        <img src="../images/logo.png" alt="logo" />
    </div>

    <div class="footer-menu">
        <ul>
            <li>Home</li>
            <li>About</li>
            <li>Services</li>
            <li>Contact</li>
        </ul>
        <p>Some text underneath the menu</p>
    </div>

    <div class="social-media">
        <ul>
            <li><a href="https://www.facebook.com/yourpage" target="_blank"><img src="path-to-facebook-icon.svg" alt="Facebook" class="social-icon"></a></li>
            <li><a href="https://www.twitter.com/yourprofile" target="_blank"><img src="path-to-twitter-icon.svg" alt="Twitter" class="social-icon"></a></li>
            <li><a href="https://www.linkedin.com/in/yourprofile" target="_blank"><img src="path-to-linkedin-icon.svg" alt="LinkedIn" class="social-icon"></a></li>
        </ul>
        <p>Connect with us on social media</p>
    </div>
</footer>
