<div id="portfolio">
  <div class="gallery-item">
    <img src="../../images/all/1.png" alt="">
    <p class="description">Description of photo 1</p>
  </div>
  <div class="gallery-item">
    <img src="../../images/all/2.png"alt="">
    <p class="description">Description of photo 2</p>
  </div>
  <!-- Repeat for additional photos -->
</div>



<style>
#portfolio {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 16px;
    padding: 16px;
}

.gallery-item {
    background-color: #f0f0f0;
    border: 2px solid #ddd;
    border-radius: 4px;
    overflow: hidden;
}

.gallery-item img {
    width: 100%;
    display: block;
}

.description {
    padding: 8px;
    text-align: center;
}
</style>
