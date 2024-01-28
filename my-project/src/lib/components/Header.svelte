<script>
  import logo from "$lib/images/logo.jpg";
</script>

<div class="h-[20%]">
  <div class="flex flex-row items-center justify-center space-x-12 p-4">
    <div>
      <img src={logo} alt="RKGIT" width="100px" height="100px" />
    </div>
    <div class="text-2xl">Raj Kumar Goel Institute of Technology</div>
  </div>
  <div
    class="flex flex-row justify-between bg-gray-100 py-2 px-24 text-gray-800"
  >
    <div><a href="/" class="hover:text-gray-500">Home</a></div>
    <div><a href="/login" class="hover:text-gray-500">Login</a></div>
    <div>
      <a href="/register" class="hover:text-gray-500">Registration</a>
    </div>
    <div>
      <a href="/catalogue/cse" class="hover:text-gray-500">Catalogue</a>
    </div>
    <div><a href="/cart" class="hover:text-gray-500">Cart</a></div>
  </div>
</div>
