<script>
</script>

<style>
    .footer {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 20px 10px;
        background-color: #0d0e11;
        color: white;
        margin-top: 3rem;
        padding-left: 3rem;
        padding-right: 3rem;
    }
    .text-footer{
    margin-top: 3rem;
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
        margin: 0 20px;
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
        width: 40px;
        height: 40px;
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
        <ul class="text-footer">
            <li class="active"><a href="/">Home</a></li>
            <li><a href="/design">Design</a></li>
            <li><a href="/coding">Coding Projects</a></li>
            <li><a href="/3d-art">3D Content</a></li>
            <li><a href="/photography">Photography</a></li>
            <li><a href="/video">Videography</a></li>
            <li><a href="/contact">Contact</a></li>
        </ul>
        <p class="text-footer">© {new Date().getFullYear()} shizuka. All rights reserved.</p>
    </div>

    <div class="social-media">
        <ul class="text-footer">
            <li><a href="https://www.linkedin.com/in/hicham-ayat-gimenez-329a90248" target="_blank"><img src="../images/linkedin.png" alt="LinkedIn" class="social-icon"></a></li>
            <li><a href="https://www.instagram.com/shizuka.desu/" target="_blank"><img src="../images/instagram.png" alt="instagram" class="social-icon"></a></li>
            <li><a href="https://github.com/TheShizuka" target="_blank"><img src="../images/github.png" alt="github" class="social-icon"></a></li>
        </ul>
        <p class="text-footer">Email - ayatgimenez@hotmail.com</p>
    </div>
</footer>
