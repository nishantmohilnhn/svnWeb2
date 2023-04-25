<script>
    import NavBar from "$lib/NavBar.svelte";
import "../app.css";
  </script>
<div class="min-h-screen flex flex-col">
  <header class=""><NavBar/></header>

  <div class="flex-1 flex flex-col sm:flex-row">
    <main class="flex-1  p-2">  <slot /> </main>

    <nav class="order-first sm:w-32  p-2 hidden sm:block">Left Navigtion bar </nav>

    <aside class="sm:w-32  p-2 hidden sm:block ">Right Sidebar</aside>
  </div>

  <footer class="bg-gray-100 p-2">Footer</footer>
</div>