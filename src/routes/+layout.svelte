<script>
	import '../Styles/styles.css'

</script>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Name or Brand</title>
    <!-- Replace the href with your chosen font's URL or link to the 'Tilt Neon' font file if it's hosted locally -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Tilt+Neon&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="styles.css">

</head>
<main>
<div class="header">
        <h1>Your Name or Brand</h1>
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
<main>
<slot></slot>
</main>

<style>
body {
    font-family: 'Tilt Neon', sans-serif; /* Update this to 'Tilt Neon' if you're using a different font */
    background-color: #FEFFED; /* Creamy beige color */
    color: black; /* Black text color */
    margin: 0;
    padding: 0;
}

.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #f7f7f7; 
    border-bottom: 2px solid #ddd;
    padding: 10px 20px;
}

.header h1 {
    margin: 0;
}

nav ul {
    display: flex;
    list-style: none;
    margin: 0; /* Remove margin */
    padding: 0; /* Remove padding */
}

nav li {
    margin-left: 15px;
}
nav a {
    text-decoration: none;
    color: black;
}

nav .active a, nav a:hover {
    text-decoration: underline;
}

.banner {
    margin: 20px 0;
	text-align: center;
}

.banner-image {
    length: 100%;
	max-length: 1000px;

}

.image-row {
    margin-bottom: 20px;
    text-align: center;
}

.image-row img {
    width: 100%;
    max-width: 1000px;
    display: block;
    margin: 10px auto;
}

button {
    background-color: #007BFF;
    color: #fff;
    border: none;
    padding: 10px 20px;
    cursor: pointer;
    border-radius: 4px;
}

button:hover {
    background-color: #FEFFED;
}
.about {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    gap: 1rem;
    padding: 2rem; /* Add padding to prevent content from touching screen borders */
}

.about img {
    max-width: 300px;
    height: auto;
    flex: 1;
    margin: 0;
    border-radius: 50%;  /* This line crops the image into a circle */
}


.text-about {
    flex: 1;
    max-width: 500px;
    padding: 0 1rem; /* Add horizontal padding for better spacing */
}

.text-about h3 {
    margin-top: 0;
}

@media (max-width: 1000px) {
    .about {
        flex-direction: column;
        padding: 1rem; /* Adjust padding for mobile */
    }

    .text-about {
        text-align: center;
        padding: 1rem 0; /* Adjust vertical padding for better spacing on mobile */
		    max-width: 90%;

    }
	.about img {
		max-width: 40%;
		height: auto;
	}
}


</style>

