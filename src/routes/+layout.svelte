<script>
    import NavBar from "$lib/NavBar.svelte";
  import Navmenu from "$lib/Navmenu.svelte";
import "../app.css";
  </script>
<div class="min-h-screen flex flex-col">
  <header class=""><NavBar/> <div class="hidden sm:block"><Navmenu/></div></header>

  <div class="flex-1 flex flex-col sm:flex-row">
    <main class="flex-1  p-2">  <slot /> </main>
    <!-- Left Navigtion bar -->
    <nav class="order-first hidden sm:block">  </nav>
<!-- right  -->
    <aside class="sm:w-32  p-2 hidden sm:block "> </aside>
  </div>
  <!-- Footer -->
  <footer class="bg-gray-100 p-2"></footer>
</div>