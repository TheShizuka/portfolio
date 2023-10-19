<script>
	import '../Styles/styles.css'
  // Wait for the DOM to finish loading before running the script
document.addEventListener('DOMContentLoaded', function() {
    // Get the navigation menu
    var navigationMenu = document.getElementById('navigation-menu');

    // Get all the menu items under the navigation menu
    var menuItems = navigationMenu.getElementsByClassName('menu-item');

    // Function to remove active class from all menu items
    function removeActiveClass() {
        for (var i = 0; i < menuItems.length; i++) {
            menuItems[i].classList.remove('active');
        }
    }

    // Attach event listener to each menu item
    for (var i = 0; i < menuItems.length; i++) {
        menuItems[i].addEventListener('click', function(event) {
            // Prevent the default action of the link
            event.preventDefault();

            // Remove active class from all other menu items
            removeActiveClass();

            // Add active class to the clicked menu item
            this.classList.add('active');
        });
    }
});

</script>
<!DOCTYPE html>
<html lang="en">
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
<div class="header">
        <h1>Your Name or Brand</h1>
        <nav>
            <ul id="navigation-menu">
                <li class="active"><a href="">Home</a></li>
                <li><a href="#">Design</a></li>
                <li><a href="#">Coding Projects</a></li>
                <li><a href="#">3D Content</a></li>
                <li><a href="#">Photography</a></li>
                <li><a href="#">Videography</a></li>
            </ul>
        </nav>
    </div>
<main>
<slot></slot>
</main>
</html>
