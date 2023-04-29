<script>
    export let imageUrl;
    export let heading;
    export let description;
    export let buttonText;
    export let buttonUrl;
  </script>
  
  <div class="relative">
    <img src={imageUrl} alt="Hero Image" class="object-cover w-full h-full">
    <div class="absolute inset-0 bg-black opacity-50"></div>
    <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 text-white text-center z-10">
      <h1 class="text-4xl font-bold">{heading}</h1>
      <p class="mt-4 text-xl">{description}</p>
      <a href={buttonUrl} class="inline-block mt-8 py-4 px-6 bg-white text-black rounded-full">{buttonText}</a>
    </div>
  </div>
  
  <style>
    .relative {
      height: 400px;
    }
    .absolute {
      width: 100%;
      max-width: 1200px;
      padding: 0 1rem;
    }
    img {
      position: absolute;
      top: 0;
      left: 0;
    }
    .bg-black {
      background-color: rgba(0, 0, 0, 0.5);
    }
  </style>
  