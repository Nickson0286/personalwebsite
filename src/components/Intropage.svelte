<script>
  import { onMount } from "svelte";
  import SectionWrapper from "./SectionWrapper.svelte";
  import Picturecarousel from "./Picturecarousel.svelte";

  let translateXLeft = 0; // For the left div
  let translateXRight = 0; // For the right div
  let opacity = 1; // For fading effect
  let displayedText = "";
  const fullText = "Hi! I'm Nguyen\nFull Stack Developer";
  let displayedParagraph = "";
  const fullParagraph =
    "My favorite tech includes JavaScript (ReactJS or SvelteKit), TailwindCSS, Node.js + Express.js & PostgreSQL.";
  let linkOpacity = 0; // For fading in the link

  onMount(() => {
    const handleScroll = () => {
      const scrollPosition = window.scrollY;
      const maxScroll = window.innerHeight;

      // Calculate translateX for fly-out effect
      translateXLeft = -scrollPosition * 0.5; // Left div flies left
      translateXRight = scrollPosition * 0.5; // Right div flies right

      // Fade out gradually as user scrolls down
      opacity = Math.max(1 - scrollPosition / maxScroll, 0); // Ensure opacity doesn't go below 0
    };

    window.addEventListener("scroll", handleScroll);

    // Typing effect for heading
    let index = 0;
    const typeText = () => {
      if (index < fullText.length) {
        displayedText += fullText[index];
        index++;
        setTimeout(typeText, 100); // Adjust typing speed here
      } else {
        // Start typing the paragraph after the heading is fully typed
        typeParagraph();
      }
    };
    typeText();

    // Typing effect for paragraph
    let paragraphIndex = 0;
    const typeParagraph = () => {
      if (paragraphIndex < fullParagraph.length) {
        displayedParagraph += fullParagraph[paragraphIndex];
        paragraphIndex++;
        setTimeout(typeParagraph, 50); // Adjust typing speed here
      } else {
        // Fade in the link after the paragraph is fully typed
        setTimeout(() => {
          linkOpacity = 1;
        }, 500); // Adjust delay here
      }
    };

    return () => {
      window.removeEventListener("scroll", handleScroll);
    };
  });
</script>

<SectionWrapper id="introPage">
  <!-- Container with overflow hidden to hide flying elements as they move out -->
  <div class="overflow-hidden">
    <div class="grid grid-cols-1 lg:grid-cols-2 py-8 sm:py-14">
      <!-- Left div with translateX and opacity for fade-out -->
      <div
        class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10"
        style="transform: translateX({translateXLeft}px); opacity: {opacity}; transition: transform 0.1s linear, opacity 0.1s linear;"
      >
        <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl lg:text-7xl">
          {#each displayedText.split("\n") as line}
            {line}<br />
          {/each}
        </h2>
        <p class="text-base sm:text-lg md:text-xl">
          {displayedParagraph}
        </p>
        <a
          class="blueShadow mx-auto lg:mr-auto lg:ml-0 text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950 cursor-pointer"
          href="https://www.linkedin.com/in/nguyen-van-2a490a81/"
          target="_blank"
          style="opacity: {linkOpacity}; transition: opacity 1s;"
        >
          <div
            class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
          ></div>
          <h4 class="relative z-9">Get in touch &rarr;</h4>
        </a>
      </div>
      <!-- Right div with translateX and opacity for fade-out -->
      <div
        class="relative shadow-2xl grid place-items-center"
        style="transform: translateX({translateXRight}px); opacity: {opacity}; transition: transform 0.1s linear, opacity 0.1s linear;"
      >
        <Picturecarousel />
        <!-- <img
          src="images/profile.png"
          alt="profile image"
          class="objective-cover z-[2] max-h-[80vh]"
        /> -->
      </div>
    </div>
  </div>
</SectionWrapper>

<style>
  .scroll-div {
    transition: opacity 0.5s;
  }
</style>
