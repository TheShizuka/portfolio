<script>
    function toggleMenu() {
        var menu = document.querySelector('.menu');
        menu.classList.toggle('open');
    }
</script>

    <div class="header">
        <button class="menu-toggle" onclick="toggleMenu()">☰</button>
        <ul class="menu">
            <li class="active"><a href="/">Home</a></li>
            <li><a href="/design">Design</a></li>
            <li><a href="/coding">Coding Projects</a></li>
            <li><a href="/3d-art">3D Content</a></li>
            <li><a href="/photography">Photography</a></li>
            <li><a href="/video">Videography</a></li>
          </ul>
    </div>


