<script>
  // @ts-nocheck

  import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/ScrollTrigger";
  import imagesLoaded from "imagesloaded";

  gsap.registerPlugin(ScrollTrigger);

  const tl = gsap.timeline();
  const preload = () => {
    tl.to(".preloader__loader__inner", {
      duration: 1,
      delay: 1,
      width: "100%",
    })
      .to(".preloader__content", {
        duration: 1,
        opacity: 0,
      })
      .to(".preloader", {
        duration: 1.4,
        y: "-100vh",
      });
  };

  const preloadBody = () => {
    document.body.style.opacity = 1;
  };

  imagesLoaded(document.querySelector("body"), function (instance) {
    preloadBody();
    preload();
  });
</script>

<main>
  <div class="preloader">
    <div class="preloader__content">
      <div class="preloader__text">The Observer</div>
    </div>
  </div>

  <div class="content">
    <div class="item">
      <div class="item__img-wrap">
        <div class="item__img item__img--t1" />
      </div>
      <div class="item__caption">
        <h2 class="item__caption-title">Central view</h2>
        <p class="item__caption-copy">
          Great turbulent clouds emerged into consciousness citizens.
        </p>
      </div>
    </div>

    <div class="item">
      <div class="item__img-wrap">
        <div class="item__img item__img--t1" />
      </div>
      <div class="item__caption">
        <h2 class="item__caption-title">Lost in time</h2>
        <p class="item__caption-copy">
          Brain is the seed of intelligence the sky calls to us a very small
          stage.
        </p>
      </div>
    </div>

    <div class="item">
      <div class="item__img-wrap">
        <div class="item__img item__img--t1" />
      </div>
      <div class="item__caption">
        <h2 class="item__caption-title">Ready to land</h2>
        <p class="item__caption-copy">
          Cosmos encyclopaedia galactica a billion trillion culture cosmic
          ocean.
        </p>
      </div>
    </div>

    <div class="item">
      <div class="item__img-wrap">
        <div class="item__img item__img--t1" />
      </div>
      <div class="item__caption">
        <h2 class="item__caption-title">All equal</h2>
        <p class="item__caption-copy">
          Network of wormholes dream of the mind's eye finite but unbounded
          concept.
        </p>
      </div>
    </div>

    <div class="item">
      <div class="item__img-wrap">
        <div class="item__img item__img--t1" />
      </div>
      <div class="item__caption">
        <h2 class="item__caption-title">Connections</h2>
        <p class="item__caption-copy">
          Two ghostly white figures in coveralls and helmets are softly dancing
          vastness.
        </p>
      </div>
    </div>

    <div class="item">
      <div class="item__img-wrap">
        <div class="item__img item__img--t1" />
      </div>
      <div class="item__caption">
        <h2 class="item__caption-title">Open perspective</h2>
        <p class="item__caption-copy">
          Vastness is bearable only through love invent the universe vanquish.
        </p>
      </div>
    </div>

    <div class="item">
      <div class="item__img-wrap">
        <div class="item__img item__img--t1" />
      </div>
      <div class="item__caption">
        <h2 class="item__caption-title">Open perspective</h2>
        <p class="item__caption-copy">
          The only home we've ever known concept of the number one.
        </p>
      </div>
    </div>

    <div class="item">
      <div class="item__img-wrap">
        <div class="item__img item__img--t1" />
      </div>
      <div class="item__caption">
        <h2 class="item__caption-title">Discovery of shapes</h2>
        <p class="item__caption-copy">
          Decipherment explorations tesseract as a patch of light.
        </p>
      </div>
    </div>

    <div class="item">
      <div class="item__img-wrap">
        <div class="item__img item__img--t1" />
      </div>
      <div class="item__caption">
        <h2 class="item__caption-title">The Observer</h2>
        <p class="item__caption-copy">
          Astonishment muse about dispassionate extraterrestrial observer.
        </p>
      </div>
    </div>
  </div>
</main>

<style>
  .preloader {
    position: fixed;
    z-index: 40;
    height: 100vh;
    width: 100vw;
    background-color: var(--color-scrollbar);
    color: var(--color-bg);
  }

  .preloader__content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
  }

  .preloader__text {
    font-weight: bold;
    font-size: 5.75rem;
    line-height: 1;
  }

  .content {
    display: flex;
    flex-direction: column;
    position: relative;
    align-items: center;
    padding: 12rem 0;
    counter-reset: figure;
  }

  .item {
    margin: 10vh auto;
    max-width: 100%;
    position: relative;
    will-change: transform;
  }

  .item::before {
    counter-increment: figure;
    content: counter(figure, decimal-leading-zero);
    position: absolute;
    font-family: var(--font-family-primary);
    font-size: 10rem;
    color: var(--color-deco);
    bottom: calc(100% - 3rem);
  }

  .item:nth-child(even)::before {
    right: 0;
  }

  .item__img-wrap {
    --aspect-ratio: 1/1.5;
    overflow: hidden;
    width: 500px;
    margin: 0 auto;
    padding-bottom: calc(100% / (var(--aspect-ratio)));
    max-width: calc(100% - 2rem);
    will-change: transform;
  }

  .item:first-child .item__img-wrap {
    --aspect-ratio: 8/10;
    --image: url("../assets/img/1.jpg");
  }

  .item:nth-child(2) .item__img-wrap {
    width: 1000px;
    --aspect-ratio: 120/76;
    --image: url("../assets/img/2.jpg");
  }

  .item:nth-child(3) .item__img-wrap {
    --aspect-ratio: 60/75;
    --image: url("../assets/img/3.jpg");
  }

  .item:nth-child(4) .item__img-wrap {
    width: 800px;
    --aspect-ratio: 900/505;
    --image: url("../assets/img/4.jpg");
  }

  .item:nth-child(5) .item__img-wrap {
    --aspect-ratio: 6/8;
    --image: url("../assets/img/5.jpg");
  }

  .item:nth-child(6) .item__img-wrap {
    width: calc(100vw - 2rem);
    --aspect-ratio: 1500/844;
    --image: url("../assets/img/6.jpg");
  }

  .item:nth-child(7) .item__img-wrap {
    width: 900px;
    --aspect-ratio: 1000/749;
    --image: url("../assets/img/7.jpg");
  }

  .item:nth-child(8) .item__img-wrap {
    width: 900px;
    --aspect-ratio: 1000/562;
    --image: url("../assets/img/8.jpg");
  }

  .item:nth-child(9) .item__img-wrap {
    --aspect-ratio: 60/75;
    --image: url("../assets/img/9.jpg");
  }

  .item__img {
    --overflow: 40px;
    height: calc(100% + (2 * var(--overflow)));
    top: calc(-1 * var(--overflow));
    width: 100%;
    position: absolute;
    background-image: var(--image);
    background-size: cover;
    background-position: 50% 0%;
    will-change: transform;
  }

  .item__img--t1 {
    --overflow: 60px;
  }

  .item__img--t2 {
    --overflow: 80px;
  }

  .item__img--t3 {
    --overflow: 120px;
  }

  .item__caption {
    padding: 2rem 1rem;
  }

  .item__caption-title {
    font-family: var(--font-family-secondary);
    font-weight: 400;
    font-size: 3rem;
    margin: 0;
  }

  .item__caption-copy {
    margin: 0;
    font-family: var(--font-family-fallback);
    line-height: 1rem;
  }

  .item__caption-copy::before {
    content: "__";
    line-height: 1;
    color: var(--color-link);
    font-weight: 700;
    font-size: 3rem;
    margin: 0 0 1rem;
    display: block;
  }
</style>
