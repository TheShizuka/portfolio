<script>
    export let design = {
        title: "",
        description: "",
        imgSrc: ""
    };
    export let isSelected = false;
    export let selectDesign = () => {};
    export let nextDesign = () => {};
    export let prevDesign = () => {};
    export let deselectDesign = () => {};
</script>


<style>
.logos {
    width: 100%; 
    max-width: 250px;
    cursor: pointer;
    display: block;
    margin: 0 auto;
    transition: transform 0.3s ease; /* This will smooth out the scaling effect */
}

.logos:hover {
    transform: scale(1.05); /* This scales the logo up by 5% on hover */
}

.overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: rgba(0, 0, 0, 0.9);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 2rem;
}

.overlay img {
    max-width: 600px;
    max-height: 600px;
    margin-bottom: 1rem;
}

.overlay h2, .overlay p {
    color: white;
    text-align: center;
    margin: 0.5rem;
}

/* Button Styles */
button {
    background: rgba(255, 255, 255, 0.3);
    border: none;
    color: white;
    padding: 0.5rem 1rem;
    margin: 0.5rem;
    cursor: pointer;
}

/* Media Queries for Responsiveness */
@media screen and (max-width: 776px) {
    .overlay img {
        max-width: 80%;
        max-height: 80%;
    }
}

/* Button Positions */
button:nth-child(4) {  /* Left Arrow */
    position: absolute;
    left: 5%;
    top: 50%;
    transform: translateY(-50%);
}

button:nth-child(5) {  /* Right Arrow */
    position: absolute;
    right: 5%;
    top: 50%;
    transform: translateY(-50%);
}

button:nth-child(6) {  /* Close Button */
    position: absolute;
    right: 5%;
    top: 5%;
}

</style>



<img class="logos" src={design.imgSrc} alt={design.title} on:click={selectDesign} />
{#if isSelected}
<div class="overlay">
    <img src={design.imgSrc} alt={design.title} />
    <h2>{design.title}</h2>
    <p>{design.description}</p>
    <button style="background-image: url('../../images/background.png'); background-repeat: repeat;" on:click={prevDesign}>&lt;</button>
    <button style="background-image: url('../../images/background.png'); background-repeat: repeat;" on:click={nextDesign}>&gt;</button>
    <button style="background-image: url('../../images/background.png'); background-repeat: repeat;" on:click={() => { isSelected = false; deselectDesign(); }}>X</button>
</div>
{/if}
