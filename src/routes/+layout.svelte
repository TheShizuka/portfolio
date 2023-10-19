<script>
  import '../Styles/styles.css'
</script>
<header>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Name or Brand</title>
    <!-- Replace the href with your chosen font's URL or link to the 'Tilt Neon' font file if it's hosted locally -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Tilt+Neon&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="styles.css">
<h1>Shizuka</h1>
        <nav>
            <ul>
                <li class="active"><a href="/">Home</a></li>
                <li><a href="/design">Design</a></li>
                <li><a href="/Developer">Coding Projects</a></li>
                <li><a href="/3D ART">3D Content</a></li>
                <li><a href="/Photography">Photography</a></li>
                <li><a href="/Videography">Videography</a></li>
            </ul>
        </nav>
</header>
<main>
<slot></slot>
</main>
</html>
