<script>
	import { onMount } from 'svelte';

	onMount(() => {
	    // Your interactive JavaScript code here
	});
</script>

<svelte:head>
	<title>Your Name or Brand</title>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Tilt+Neon&display=swap" rel="stylesheet">
	<link rel="stylesheet" href="/styles.css">
</svelte:head>

<body>
    <header>
        <h1>Your Name or Brand</h1>
        <nav>
            <ul>
                <li class="active"><a href="#">Home</a></li>
                <li><a href="#">Design</a></li>
                <li><a href="#">Coding Projects</a></li>
                <li><a href="#">3D Content</a></li>
                <li><a href="#">Photography</a></li>
                <li><a href="#">Videography</a></li>
            </ul>
        </nav>
    </header>
    <div class="banner">
        <img src="images/banner.png" alt="Banner Description" class="banner-image">
    </div>
    <!-- Image Rows with "Learn More" buttons -->
	<div class="about">
        <img src="images/profile-picture.png" alt="Learn more about my photography skills">
		<div class="text-about">
		<h3>Shizuka</h3>
        <p>Passionate and versatile digital creator with a diverse skill set spanning video/photo editing, 3D
			modeling, 2D art, and web development. Proficient in Adobe Suite, including Photoshop,
			Illustrator, Premiere Pro, and After Effects. Eager to contribute to innovative projects with a keen
			interest in remote roles related to video/photo creation, web design, and 3D artistry. Committed
			to continuous learning and growth in the digital domain. In addition to my digital creation skills,
			I also possess coding expertise, enabling me to develop and implement technical solutions for
			various projects.
			</p>
		</div>
    </div>
    <div class="image-row">
        <img src="images/photography.png" alt="Learn more about my photography skills">
        <button>Learn More</button>
    </div>
    <div class="image-row">
        <img src="path_to_image2.jpg" alt="Description of Image 2">
        <button>Learn More</button>
    </div>
    <div class="image-row">
        <img src="path_to_image3.jpg" alt="Description of Image 3">
        <button>Learn More</button>
    </div>
</body>

<style>
	body {
    font-family: 'Tilt Neon', sans-serif; /* Update this to 'Tilt Neon' if you're using a different font */
    background-color: #FEFFED; /* Creamy beige color */
    color: black; /* Black text color */
    margin: 0;
    padding: 0;
}

header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #f7f7f7; 
    border-bottom: 2px solid #ddd;
    padding: 10px 20px;
}

header h1 {
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
