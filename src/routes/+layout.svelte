<script>
    import NavBar from "$lib/NavBar.svelte";
  import Navmenu from "$lib/Navmenu.svelte";
import "../app.css";
  </script>
<div class="min-h-screen flex flex-col">
  <header class=""><NavBar/> <div class="hidden sm:block"><Navmenu/></div></header>

  <div class="flex-1 flex flex-col sm:flex-row">
    <main class="flex-1 p-1">  <slot /> </main>
  </div>
  <!-- Footer -->
  <footer class="bg-gray-100 p-2"></footer>
</div>