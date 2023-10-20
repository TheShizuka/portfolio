<script>
	import '../Styles/styles.css'
</script>
<header>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Shizuka's Portfolio</title>
	<!-- Replace the href with your chosen font's URL or link to the 'Tilt Neon' font file if it's hosted locally -->
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Tilt+Neon&display=swap" rel="stylesheet">
	<div class="header">
        	<nav>
            		<ul>
                		<li class="active"><a href="/">Home</a></li>
                		<li><a href="/design">Design</a></li>
		                <li><a href="/coding">Coding Projects</a></li>
		                <li><a href="/3d-art">3D Content</a></li>
		                <li><a href="/photography">Photography</a></li>
		                <li><a href="/video">Videography</a></li>
            		</ul>
		</nav>
    	</div>

</header>

<main>

	<slot />

</main>


