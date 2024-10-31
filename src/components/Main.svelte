<script>
// @ts-nocheck
  import {slide, fly} from 'svelte/transition'
  import Step from "./Step.svelte"
  import Intropage from "./Intropage.svelte";
  import About from "./About.svelte";
  import {onMount, onDestroy} from 'svelte';

  let opacity = 0;
  let divElement;

  onMount(() => {
    const handleScroll = () => {
      const scrollPosition = window.scrollY;
      const maxScroll = window.innerHeight;

      // Update opacity based on scroll position
      opacity = Math.min(scrollPosition / maxScroll /1.3, 2);
    };

    window.addEventListener('scroll', handleScroll);

    return () => {
      window.removeEventListener('scroll', handleScroll);
    };
  });


  let transition = false;

  let steps = [
    {name: "Office Ally Clone", icon:" fa-solid fa-calendar-check", description: `Office Ally is a web application created with React.js, TailwindCSS, Node.js, Express.js. It allows medical staff to schedule, create, and manage patients' appointments and charts.`},
    {name: "Speech-To-Text Transcriptor", icon:" fa-solid fa-comment-dots", description: `Google Speech-To-Text Transcriptor is a web application allow user to record and transcribe their voice into text and display it on web page, created with React.js, TailwindCSS, Node.js Express.js, & Google Cloud Speech To Text API`},
    {name: "Gym App Generator", icon:" fa-solid fa-dumbbell", description: `Gym App Generator is a web application created with React.js, TailwindCSS, Node.js, Express.js, & PostgreSQL. It allows users to generate a custom workout plan based on their fitness goals and preferences.`, href:'https://gym-training-generator.netlify.app/'},
    {name: "Ooh La La Salon", icon:"fa-solid fa-paintbrush", href:"https://oohlalasalon.netlify.app", description: `a custom salon appointment management system with a landing page, featuring seamless scheduling, customer management, and automated notifications. Focused on an intuitive user interface while optimizing backend performance for efficient data processing. Technologies used include SvelteKit, TailwindCSS, Node.js, Express.js, and PostgreSQL.`},
  ]

  
</script>

<main class="flex flex-col flex-1 p-4">
  <Intropage />
  <section id="projects" class="py-20 lg:py-32 flex flex-col gap-24" in:fly={{ y: 200, duration: 1000 }} >
    <div class="flex flex-col gap-2 text-center">
      <h6 class="text-large sm:text-xl md:text-2xl">A Few of my creative endeavors</h6>
      <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
        Curious to <span class="poppins text-violet-400">see</span> my work?
      </h3> 
    </div>
    <!-- <a href="" target="_blank" class="mx-auto px-4 py-2 rounded-md border border-solid border-white flex items-center gap-2 -mb-4 sm:-mb-0 -mt-10 hover:border-violet-700 duration-200">
      <i class="fa-regular fa-circle-play"></i>
      <p class="">Watch the video</p>
    </a> -->
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 lg:gap-10 scroll-div" style='opacity: {opacity}'>
      {#each steps as project}
        <Step step={project}/>
      {/each}
    </div>
  </section>
  <About />
</main>

<style>
  .scroll-div {
    transition: opacity 0.2s;
  }
</style>