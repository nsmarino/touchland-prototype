<script>
  import App from '$lib/components/App.svelte'
    import { onMount } from 'svelte';



onMount(() => {
  const intersectionCallback = (entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        let elem = entry.target;

        if (entry.intersectionRatio > 0) {
          window.scrollTo({
            top: 0,
          });
          document.querySelectorAll(".bg-card").forEach((bg) => {
            bg.classList.remove("unfixed");
          });
        }
      }
    });
  };

  const options = {
    threshold: 0.5,
  };

  const observer = new IntersectionObserver(intersectionCallback, options);
  const target = document.querySelector("#target");

  observer.observe(target);

  const entranceManager = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add("animate");
        if (entry.target.querySelector("img")) {
          entry.target.parentElement.querySelector(".bg-card").classList.add("unfixed")
        }
      } else {
          entry.target.classList.remove("animate");
      }
    });
  }, {
    threshold: 0.75
  });
  const entranceUsers = document.querySelectorAll(".entrance");
  entranceUsers.forEach((user) => {
    entranceManager.observe(user);
  });


  // end onMount
});



</script>

  <!-- <App /> -->
  
  <header class="omit-from-repeat">
    <div>touchland</div>
    <div style="display: flex; gap: 16px;">
      <div>00:31:24:12</div>
      <div>Join the Waitlist</div>
    </div>
  </header>
  <div class="hero omit-from-repeat">
    <p>New</p>
    <h1>Meet Body Mist.</h1>
    <p>Mood-boosting formulas for soothed skin and uplifted senses.</p>
    <button>Join the waitlist</button>
  </div>

  <!-- Product 1 -->
  <div class="lifestyle-card omit-from-repeat">
  </div>
  <div class="fullscreen-card entrance lifestyle-text-card">
    <div class="text">I want to</div>
  </div>
  <div class="fullscreen-card"></div>
  
  <div class="product-card">
    <div class="bg-card"></div>
    <div class="fullscreen-card entrance product-text-card">
      <div class="text">feel transformed.</div>
    </div>
    <div class="fullscreen-card entrance">
      <img src="/ProductModel.png" alt="">
      <p>Lush Tropicale</p>
    </div> 
  </div>

  <!-- Product 2 -->
  <div class="lifestyle-card secondproduct">
  </div>
  <div class="fullscreen-card entrance lifestyle-text-card">
    <div class="text">I want to</div>
  </div>
  
  <div class="product-card secondproduct">
    <div class="bg-card secondproduct"></div>
    <div class="fullscreen-card entrance entrance product-text-card">
      <div class="text">feel transformed.</div>
    </div>
    <div class="fullscreen-card entrance">
      <img src="/ProductModel.png" alt="">
      <p>Lush Tropicale</p>
    </div> 
  </div>

  <!-- Product 3 -->
  <div class="lifestyle-card thirdproduct">
  </div>
  <div class="fullscreen-card entrance lifestyle-text-card">
    <div class="text">I want to</div>
  </div>
  
  <div class="product-card thirdproduct">
    <div class="bg-card thirdproduct"></div>
    <div class="fullscreen-card entrance product-text-card">
      <div class="text">feel transformed.</div>
    </div>
    <div class="fullscreen-card entrance">
      <img src="/ProductModel.png" alt="">
      <p>Lush Tropicale</p>
    </div> 
  </div>

  <div class="hero">
    <p>New</p>
    <h1>Meet Body Mist.</h1>
    <p>Mood-boosting formulas for soothed skin and uplifted senses.</p>
    <button>Join the waitlist</button>
  </div>
  <div class="lifestyle-card" id="target">
  </div>

  

<style>
  :global(body) {
    margin: 0;
    padding: 0;
  }

  header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 3;
    font-family: Arial, Helvetica, sans-serif;
    font-weight: bolder;
    color: black;
    background: white;
    display: flex;
    justify-content: space-between;
    padding: 16px;
    border-bottom: 1px solid #B3B3B3;
  }

  .bg-card {
      width: 100vw;
      height: 100vh;
      z-index: 1;
      position: sticky;
      top: 0;
      color: white;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background-image: url(/ProductBG.png);
      background-size: cover;
      background-attachment: fixed;
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

  .product-text-card {
    margin-top: -75vh;
  }
  .lifestyle-text-card {
    margin-top: -50vh;
  }
  .hero {
    height: 50vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 0 20px 40px;
    position: relative;
    z-index: 2;
    background: white;
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
    background: url(/LifestyleBG.png);
    background-size: cover;

  }
  .fullscreen-card {
    width: 100vw;
    height: 100vh;
    z-index: 1;
    position: sticky;
    top: 0;
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background: transparent;
  }

  .halfscreen-card {
    width: 100vw;
    height: 50vh;
    z-index: 1;
    position: relative;
    background: transparent;
  }
  .product-card {
    width: 100vw;
    height: 400vh;
    background-image: url(/ProductBG.png);
    background-size: cover;
    background-attachment: fixed;
    background-position: top;
    background-repeat: no-repeat;
    position: relative;
    z-index: 1;
    top: 0;
    color: white;
  }
  .lifestyle-card.secondproduct {
    background-image: url(/LifestyleBG2.png);
  }
  .bg-card.secondproduct {
    background-image: url(/ProductBG2.png);
  }
  
  .bg-card.thirdproduct {
    background-image: url(/ProductBG3.png);
  }
  .lifestyle-card.thirdproduct {
    background-image: url(/LifestyleBG3.png);
  }

</style>
