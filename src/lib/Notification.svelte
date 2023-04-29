<script>
  import { onMount } from 'svelte';
let notifications = [];

async function fetchNotifications() {
  const response = await fetch('https://cool-cloud-2974.fly.dev/api/collections/notification_public/records');
  const data = await response.json();
  notifications = data.items.slice().reverse();
}

onMount(async () => {
  await fetchNotifications();
})
  </script>
  <div class=" bg-slate-50 m-1 rounded-md overflow-hidden drop-shadow-md shadow-slate-800 max-w-5xl mx-auto ">
    <div>
      <p class=" bg-blue-900 text-white text-center font-semibold  "> Notifications</p>
    </div>
    <div>
      {#if notifications.length > 0}
      <ul>
          {#each notifications as notification}
              <li>{notification.title} 
                {#if notification.pdf_link!=""}
                <div class=" ml-4 ">
                  <a href="{notification.pdf_link}" class=" bg-orange-300 rounded-full font-bold"> View more </a>
                </div>
                {/if}
              </li>
          {/each}
        </ul>
        {:else}
        <p> loading ... </p>
        {/if}
    </div>

  </div>


  

