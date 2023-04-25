<script>
	import { fly } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
    let show = false;
</script>
<nav class="flex justify-between bg-pink-800 p-1">
    <div class="flex items-center gap-2">
      <img class="h-8 w-10" src="https://cool-cloud-2974.fly.dev/api/files/x5e0bsbfhuqtpd6/8nlbeyzxeox2to5/group_1_wkXMUld7wH.png" alt="logo S V N school " />
      <p class="text-white">SHISHU VIDYA NIKETAN</p>
    </div>
    <div class="mr-2 sm:hidden">
      <button on:click={()=> show = !show}>
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="h-6 w-6 text-white">
          <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5M12 17.25h8.25" />
        </svg>
      </button>
    </div>
  </nav>
  {#if show}
  <div 
  transition:fly="{{delay:50, duration: 300, x: 100, opacity: 0.5, easing: quintOut}}"
  class="fixed right-0 h-screen w-5/6 bg-red-300 sm:hidden z-10 ">
    <div class="ml-11 mt-14 font-semibold text-white">
      <a class="mt-7 block" href="/">Home</a>
      <a class="mt-7 block" href="/">Home</a>
      <a class="mt-7 block" href="/">Home</a>
      <a class="mt-7 block" href="/">Home</a>
      <a class="mt-7 block" href="/">Home</a>
      <a class="mt-7 block" href="/">Home</a>
    </div>
  </div>
  {/if}
