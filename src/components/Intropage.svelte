<script>
  import SectionWrapper from "./SectionWrapper.svelte";
</script>

<SectionWrapper id="introPage">
<div  class="grid gird-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14 ">
  <div class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10">
    <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
      Hi! I'm <span class="poppins text-violet-400">Nguyen</span> Van <br/>Full Stack <span class="poppins text-violet-400">Developer</span>
    </h2>
    <p class="text-base sm:text-lg md:text-xl">My <span class="text-violet-400">favorite tech</span> includes JavaScript (ReactJS or SvelteKit), TailwindCSS, Node.js + Express.js & PostgreSQL.</p>
    <a class="blueShadow mx-auto lg:mr-auto lg:ml-0 text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950 cursor-pointer" href="https://www.linkedin.com/in/nguyen-van-2a490a81/" target="_blank" >
      <div class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200">
      </div>
      <h4 class="relative z-9">Get in touch &rarr;</h4>
    </a>
  </div>
  <div class="relative shadow-2xl grid place-items-center">
    <img src={"images/profile.png"} alt="profile image" class="objective-cover z-[2] max-h-[80vh]"/>
  </div>
</div>
</SectionWrapper>