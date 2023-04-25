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
        <ul>
            {#each notifications as notification}
                <li>{notification.title} {#if notification.pdf_link!=""}
                    <a href="{notification.pdf_link}" class=" bg-orange-300 rounded-full p-2 font-bold"> View more </a>
                {/if}</li>
            {/each}
          </ul>
  {:else}
 <p> loading ... </p>
  {/if}
  