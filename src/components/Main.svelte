<script>
  import Step from "./Step.svelte"
  import Intropage from "./Intropage.svelte";
  import About from "./About.svelte";

  let steps = [
    {name: "Office Ally Clone", icon:" fa-solid fa-calendar-check"},
    {name: "Speech-To-Text Transcriptor", icon:" fa-solid fa-comment-dots"},
  ]

  
</script>

<main class="flex flex-col flex-1 p-4">
  <Intropage />
  <section id="projects" class="py-20 lg:py-32 flex flex-col gap-24">
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
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 lg:gap-10">
      
      <Step step={steps[0]}>
        <p>Office Ally is a web application created with <strong class="text-violet-400">React.js TailwindCSS </strong> & <strong class="text-violet-400">Node.js </strong> + <strong class="text-violet-400">Express.js</strong> & <strong class="text-violet-400">PostgreSQL</strong>. It allows medical staff to schedule, create, and manage patients' appointments and charts.
        </p>
      </Step>
      <Step step={steps[1]}>
        <p>Google Speech-To-Text Transcriptor is a web application allow user to record and transcribe their voice into text and diplay it on web page, created with <strong class="text-violet-400">React.js TailwindCSS </strong> & <strong class="text-violet-400">Node.js </strong> + <strong class="text-violet-400">Express.js</strong> & <strong class="text-violet-400">Google Cloud Speech To Text API</strong>.
      </Step>
      
    </div>
  </section>
  <About />
</main>