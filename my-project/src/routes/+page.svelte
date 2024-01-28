<script>
  import Header from "$lib/components/Header.svelte";
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>

<section class="h-screen">
  <Header />
  <div
    class="h-[80%] flex flex-row bg-gradient-to-r from-indigo-500 from-10% via-sky-500 via-30% to-emerald-500 to-90%"
  >
    <div
      class="flex flex-col w-1/6 items-center space-y-12 border-r py-16 bg-gray-400"
    >
      <div><a href="/catalogue/cse">CSE</a></div>
      <div><a href="/catalogue/ece">ECE</a></div>
      <div><a href="/catalogue/eee">EEE</a></div>
      <div><a href="/catalogue/civil">CIVIL</a></div>
    </div>
    <div class="w-5/6 p-12">The description of the course goes here.</div>
  </div>
</section>
