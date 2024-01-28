<script>
  import Header from "$lib/components/Header.svelte";
</script>

<section class="h-screen">
  <Header />
  <div
    class="flex flex-col items-center justify-center bg-gradient-to-r from-indigo-500 from-10% via-sky-500 via-30% to-emerald-500 to-90% h-[80%]"
  >
    <div class="bg-white p-8 w-2/5 rounded-lg">
      <h1 class="text-xl font-bold text-gray-700 mb-2">Login</h1>
      <form id="login-form" class="flex flex-col">
        <label for="email" class="text-sm text-gray-500">Email</label>
        <input
          type="email"
          name="email"
          id="email"
          placeholder="Email"
          class="border p-2 mb-2 rounded-md"
          required
        />
        <label for="password" class="text-sm text-gray-500">Password</label>
        <input
          type="password"
          name="password"
          id="password"
          placeholder="Password"
          class="border p-2 mb-2 rounded-md"
          required
        />

        <button
          id="login"
          class="bg-gray-600 text-gray-100 rounded-md p-2 hover:bg-gray-500"
          type="submit"
        >
          Login
        </button>
      </form>
    </div>
  </div>
</section>
