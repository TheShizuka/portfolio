

<div id="portfolio">
  <div class="image-group">
    <img src="../../images/all/1.png" alt="" class="small">
    <img src="../../images/all/3.png"  alt="" class="large">
    <img src="../../images/all/4.png"  alt="" class="small">
    <img src="../../images/all/50.png"  alt="" class="large">
  </div>
</div>



<style>
body {
    background-color: #0D0E11;
}

#portfolio {
    padding: 16px;
}

.image-group {
    display: grid;
    grid-template-columns: 2fr 1fr;
    grid-template-rows: 1fr 1fr;
    gap: 4px;
    width: 1280px;
    height: 720px;
    overflow: hidden;
}

.large {
    grid-row: span 2;
    object-fit: cover;
}

.small {
    object-fit: cover;
}

</style>
