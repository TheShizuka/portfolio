<script>
</script>

<style>
    .footer {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 20px 10px;
        color: white;
        padding-left: 3rem;
        padding-right: 3rem;
        flex-direction: column;
    }
    .text-footer{
    margin-top: 3rem;
    }
    .social-logo-footer{
    margin-top: 2rem;
    }

    .footer-logo img {
        width: 50px; /* Adjust based on your preference */
        height: auto;
        margin-top: 1rem;
        margin-bottom: 1rem;

}
    .footer-logo {
        text-align: center;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .footer-menu {
        text-align: center;
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-left: 5rem;
        margin-right: 5rem;
    }

     .footer-menu a {
        text-decoration: none;   /* Remove underline */
        color: white;            /* Set color to white */
        transition: 0.3s; 
        
    }

    .footer-menu a:hover {
        text-decoration: underline;  /* Underline on hover */
    }
    

    .footer-menu ul {
        list-style: none;
        padding: 0;
        display: table-cell;
    }

    .footer-menu li {
        display: inline;
        margin: 0 20px;
        list-style: outside none none;
        display: inline-block;
    }

    .social-media {
        display: flex;
        flex-direction: column;
        align-items: center;
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

    }
</style>

<footer class="footer" style="background-image: url('../../images/background.png'); background-repeat: repeat;">
    <div class="footer-logo">
        <img src="../images/logo.png" alt="logo" />
        <p class="text-footer">Hicham Ayat</p>
    </div>

    <div class="footer-menu">
        <ul class="text-footer">
            <li class="active"><a href="/">Home</a></li>
            <li><a href="/photography">Photography</a></li>
            <li><a href="/3dart">3D Art</a></li>
            <li><a href="/design">Design</a></li>
            <li><a href="/coding">Coding Projects</a></li>
            <li><a href="/video">Videography</a></li>
            <li><a href="/contact">Contact</a></li>
        </ul>
        <p class="text-footer">© {new Date().getFullYear()} shizuka. All rights reserved.</p>
    </div>

    <div class="social-media">
        <ul class="social-logo-footer">
            <li><a href="https://www.linkedin.com/in/hicham-ayat-gimenez-329a90248" target="_blank"><img src="../images/linkedin.png" alt="LinkedIn" class="social-icon"></a></li>
            <li><a href="https://www.instagram.com/shizuka.desu/" target="_blank"><img src="../images/instagram.png" alt="instagram" class="social-icon"></a></li>
            <li><a href="https://github.com/TheShizuka" target="_blank"><img src="../images/github.png" alt="github" class="social-icon"></a></li>
        </ul>
        <p class="text-footer">Email - ayatgimenez@hotmail.com</p>
    </div>
</footer>
