<script>
  import Lenis from "@studio-freight/lenis";
  import Home from "./components/Home.svelte";
  import Navbar from "./components/Navbar.svelte";

  const lenis = new Lenis({
    duration: 5,
    easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
    direction: "vertical",
    gestureDirection: "vertical",
    smooth: true,
    mouseMultiplier: 1,
    smoothTouch: false,
    touchMultiplier: 2,
    infinite: false,
  });

  //get scroll value
  lenis.on("scroll", ({ scroll, limit, velocity, direction, progress }) => {
    console.log({ scroll, limit, velocity, direction, progress });
  });

  /**
   * @param {any} time
   */
  const raf = (time) => {
    lenis.raf(time);
    requestAnimationFrame(raf);
  };

  requestAnimationFrame(raf);
</script>

<main>
  <Navbar />
  <Home />
</main>
