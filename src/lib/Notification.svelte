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
  
  {#if notifications.length > 0}
  <div class=" bg-gray-50 rounded-xl shadow-lg overflow-hidden m-3">
    <div class=" bg-gray-500 drop-shadow-md">
    <p class=" text-center font-bold text-white "> Notification </p>
    </div>
    <div class="py-1 m-1 max-w-2xl mx-auto">
        <ul>
            {#each notifications as notification}
                <li>{notification.title} {#if notification.pdf_link!=""}
                    <a href="{notification.pdf_link}" class=" bg-orange-300 rounded-full p-2 font-bold"> View more </a>
                {/if}</li>
            {/each}
          </ul>
    </div>
  
  </div>
       
  {:else}
  <div class="absolute bg-white bg-opacity-60 z-10 flex items-center justify-center">
    <div class="flex items-center">
      <span class="text-3xl mr-4">Loading</span>
      <!-- loading icon -->
      <svg class="animate-spin h-5 w-5 text-gray-600" xmlns="http://www.w3.org/2000/svg" fill="none"
        viewBox="0 0 24 24">
        <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
        <path class="opacity-75" fill="currentColor"
          d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z">
        </path>
      </svg>
      <!-- end loading icon -->
    </div>
  </div>
  {/if}
  