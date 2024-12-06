<script>
  import App from '$lib/components/App.svelte'
</script>

  <!-- <App /> -->
  
  <header>touchland</header>
  <div class="hero">
    <p>New</p>
    <h1>Meet Body Mist.</h1>
    <p>Mood-boosting formulas for soothed skin and uplifted senses.</p>
    <button>Join the waitlist</button>
  </div>
  <div class="lifestyle-card">
    <!-- <div class="text">I want to feel</div> -->
  </div>
  <div class="text-card">
    <div class="text">I want to</div>
  </div>
  <div class="product-card">
    <!-- <div class="text">HAPPINESS</div>
    <div class="product-image">
      <img src="ProductModel.png" alt="">
    </div> -->
    <div class="text-card"></div>
    <div class="text-card">
      <div class="text">feel transformed.</div>
    </div>
    <div class="text-card">
      <img src="ProductModel.png" alt="">
      <p>Lush Tropicale</p>
    </div> 
  </div>
  <div class="lifestyle-card" style="background-image: url(LifestyleBG2.png)">
    <!-- <div class="text">I want to feel</div> -->
  </div>
  <div class="text-card">
    <div class="text">I want to</div>
  </div>
  <div class="product-card secondproduct">
    <div class="text-card"></div>
    <div class="text-card">
      <div class="text">express not repress.</div>
    </div>
    <div class="text-card">
      <img src="ProductModel2.png" alt="">
      <p>Cashmere Woods</p>

    </div> 
  </div>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
  }
  header {
    position: fixed;
    z-index: 2;
    font-family: Arial, Helvetica, sans-serif;
    padding: 2px;
    background-color: rgba(255, 255, 255, 0.5);
    color: black;
    width: 100vw;
  }
  
  p {
    font-size: 10px;
    text-transform: uppercase;
    font-family: Arial, Helvetica, sans-serif;
  }
  .text {
    font-size: 32px;
    font-family: Arial, Helvetica, sans-serif;

  }
  .hero {
    top: 0;
    padding: 80px 0 20px;
  }
  .lifestyle-card {
    width: 100vw;
    height: 100vh;
    z-index: 1;
    position: sticky;
    top: 0;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    background: url(LifestyleBG.png);
    background-size: cover;

  }
  .text-card {
    width: 100vw;
    height: 100vh;
    z-index: 1;
    position: relative;
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background: transparent;
  }
  .product-image {
    width: 40%;
    background: green;
    height: 70%;
    border-radius: 20px;
  }
  .product-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 20px;
  }
  .product-card {
    width: 100vw;
    height: 300vh;
    background: url(ProductBG.png);
    background-size: cover;
    background-attachment: fixed;
    background-position: top;
    background-repeat: no-repeat;
    position: relative;
    z-index: 1;
    top: 0;
    color: white;
  }
  .product-card.secondproduct {
    background-image: url(ProductBG2.png);
  }

  /* div {
    width: 100vw;
    height: 100vh;
    background: white;
  } */
</style>
