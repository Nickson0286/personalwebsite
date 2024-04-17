<script>
  import SectionWrapper from "./SectionWrapper.svelte";
  let benefits = [
    {name: 'a self taught developer', description:"I taught myself to code using multiple resources including University's curriculum, free online tutorial, and coding bootcamps, and I feel in love with the creativity and problem solving that is involed in developing and engineering innovative online experiences. Starting with JavaScript, HTML & CSS and evolving my knowledge base to include JavaScript frameworks, backend programming, design, cloud services and much more."},
    {name: 'a product design and back-end enthusiatic', description:"Seasoned in utilizing Node.js, I bring a wealth of experience in constructing robust backend servers for diverse software applications, employing various technologies and implementing rigorous security measures. My proficiency ensures the development of reliable and secure server-side solutions tailored to meet the unique requirements of each project."},
    {name: 'an excellent communicator', description:'Communication is key and it\'s a paramount value of mine. I believe in transparency and constructive conmmunication above all else. This helps me develop deep relationships and ensures my effectiveness and productivity in any work space with any team.'},
  ]

</script>
<SectionWrapper id=about>
  <div class="py-20 pt-10 lg:pt-16 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative">
  <div class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4">
    <h6 class="text-lg sm:text-xl md:text-2xl">Want to know more?</h6>
    <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">A bit <span class="poppins text-violet-400">about </span>me.
    </h3>
  </div>
  <p class="mx-auto poppins font-semibold text-xl sm:text-xl md:text-2xl">I am . . .</p>
  <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
    {#each benefits as benefit, index}
      <div class="flex gap-6 sm:gap-8">
       <p class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold">0{index+1}</p>
       <div class="flex flex-col gap-6 sm:gap-8"><h3 class="text-2xl sm:text-3xl md:text-5xl">{benefit.name}</h3>
        <p>{benefit.description}</p>
      </div>
      </div>
      
    {/each}
  </div>
  <h5 class="text-2xl sm:text-3xl font-semibold text-center poppins"> The <span class="text-violet-400 poppins">Complete</span> Package</h5>
  <div class="flex flex-col overflow-x-scroll gap-10 mx-w-[800px] mx-auto">
    <table class="bg-white text-slate-700 rounded text-center">
      <thread class="border-b border-solid border-slate-200">
        <tr class="">
          <th/>

          <th class="whitespace-nowrap p-2 px-4">Candidate #1</th>
          <th class="whitespace-nowrap p-2 px-4">Candidate #2</th>
          <th class="whitespace-nowrap p-2 px-4">Candidate #3</th>
          <th class="whitespace-nowrap bg-violet-700 text-white p-4 px-8">Me</th>
        </tr>
        <tbody>
          <tr class="border-b border-solid border-slate-200">
            <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap">Dedication</td>
            <td class=""><i class="fa-solid fa-check text-slate-500"></i></td>
            <td class=""><i class="fa-solid fa-xmark text-slate-500"></i></td>
            <td class=""><i class="fa-solid fa-check text-slate-500"></i></td>
            <td class=""><i class="fa-solid fa-check text-green-500"></i></td>
          </tr>
          <tr class="border-b border-solid border-slate-200">
            <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap">Critical Thinking</td>
            <td class=""><i class="fa-solid fa-xmark text-slate-500"></i></td>
            <td class=""><i class="fa-solid fa-check text-slate-500"></i></td>
            <td class=""><i class="fa-solid fa-xmark text-slate-500"></i></td>
            <td class=""><i class="fa-solid fa-check text-green-500"></i></td>
          </tr>
          <tr class="border-b border-solid border-slate-200">
            <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap">Interpersonal Skills</td>
            <td class=""><i class="fa-solid fa-xmark text-slate-500"></i></td>
            <td class=""><i class="fa-solid fa-check text-slate-500"></i></td>
            <td class=""><i class="fa-solid fa-check text-slate-500"></i></td>
            <td class=""><i class="fa-solid fa-check text-green-500"></i></td>
          </tr>
          <tr class="border-b border-solid border-slate-200">
            <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap">Programming Ability</td>
            <td class=""><i class="fa-solid fa-check text-slate-500"></i></td>
            <td class=""><i class="fa-solid fa-xmark text-slate-500"></i></td>
            <td class=""><i class="fa-solid fa-xmark text-slate-500"></i></td>
            <td class=""><i class="fa-solid fa-check text-green-500"></i></td>
          </tr>
        </tbody>
      </thread>
      </table>
  </div>
  <div class="mx-auto -mt-12 italic sm:hidden opacity-50">
    <p>Scroll to see more &rarr;</p>
  </div>
  <p class="mx-auto">So why not invest?</p>
</div>
</SectionWrapper>
