<script>
  import image1 from "$lib/assets/svelte.png";
  import image2 from "$lib/assets/react.png";
  import image3 from "$lib/assets/vue.png";
  import image4 from "$lib/assets/node.png";
  import image5 from "$lib/assets/postgre.png";
  import image6 from "$lib/assets/mongoDB.png";
  import image7 from "$lib/assets/graphql.png";
  import image8 from "$lib/assets/google.png";
  import image9 from "$lib/assets/git.png";
  import image10 from "$lib/assets/js.png";
  import image11 from "$lib/assets/html.png";
  import image12 from "$lib/assets/css.png";
</script>

<div class="banner">
  <div class="slider">
    <div class="item" style="--position: 1">
      <img src={image1} alt="pic 1" />
    </div>
    <div class="item" style="--position: 2">
      <img src={image2} alt="pic 2" />
    </div>
    <div class="item" style="--position: 3">
      <img src={image3} alt="pic 3" />
    </div>
    <div class="item" style="--position: 4">
      <img src={image4} alt="pic 4" />
    </div>
    <div class="item" style="--position: 5">
      <img src={image5} alt="pic 5" />
    </div>
    <div class="item" style="--position: 6">
      <img src={image6} alt="pic 6" />
    </div>
    <div class="item" style="--position: 7">
      <img src={image7} alt="pic 7" />
    </div>
    <div class="item" style="--position: 8">
      <img src={image8} alt="pic 8" />
    </div>
    <div class="item" style="--position: 9">
      <img src={image9} alt="pic 9" />
    </div>
    <div class="item" style="--position: 10">
      <img src={image10} alt="pic 10" />
    </div>
    <!-- <div class="item" style="--position: 11">
      <img src={image11} alt="pic 11" />
    </div>
    <div class="item" style="--position: 12">
      <img src={image12} alt="pic 12" />
    </div>
    <div class="item" style="--position: 13">
      <img src={image13} alt="pic 13" />
    </div> -->
  </div>
</div>

<style>
  .banner {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    perspective: 1000px;
    overflow: hidden;
  }

  .slider {
    width: 200px;
    height: 250px;
    top: 10%;
    left: calc(50% - 100px);
    position: absolute;
    transform-style: preserve-3d;
    animation: rotate 40s infinite linear;
  }

  .item {
    width: 100px;
    height: 100px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: rotateY(calc(var(--position) * 36deg)) translateZ(250px);
  }

  @keyframes rotate {
    0% {
      transform: rotateX(-16deg) rotateY(0deg);
    }
    25% {
      transform: rotateX(0deg) rotateY(90deg);
    }
    50% {
      transform: rotateX(16deg) rotateY(180deg);
    }
    75% {
      transform: rotateX(0deg) rotateY(270deg);
    }
    100% {
      transform: rotateX(-16deg) rotateY(360deg);
    }
  }
</style>
