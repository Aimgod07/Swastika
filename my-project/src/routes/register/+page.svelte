<script>
  import Header from "$lib/components/Header.svelte";

  function handleRegister(e) {
    console.log(e);
    const form = e.target;

    if (!form.password.length > 5 || !form.password2.length > 5) {
      alert("Password should be at least 6 characters long");
      return;
    }

    if (form.password.value !== form.password2.value) {
      alert("Passwords do not match");
      return;
    }

    if (!form.name.length > 5) {
      alert("Name should be at least 6 characters long");
      return;
    }

    if (parseInt(form.phone.value) < 1000000000) {
      alert("Phone number should be 10 digits long");
      return;
    }

    localStorage.setItem(
      "user",
      JSON.stringify({
        name: form.name.value,
        email: form.email.value,
        password: form.password.value,
      })
    );
    window.location.href = "/";
    console.log(JSON.parse(localStorage.getItem("user")));
  }
</script>

<section class="h-full">
  <Header />
  <div
    class="flex flex-col items-center justify-center bg-gradient-to-r from-indigo-500 from-10% via-sky-500 via-30% to-emerald-500 to-90% h-full py-16"
  >
    <div class="bg-white p-8 w-2/5 rounded-lg">
      <h1 class="text-xl font-bold text-gray-700 mb-2">Register</h1>
      <form
        on:submit={handleRegister}
        id="register-form"
        type="post"
        class="flex flex-col w-full"
      >
        <label for="name" class="font-medium text-sm text-gray-500">Name</label>
        <input
          type="text"
          name="name"
          id="name"
          placeholder="Name"
          class="mt-1 border p-2 mb-2 rounded-md"
          minlength="6"
          required
        />
        <label for="email" class="font-medium text-sm text-gray-500"
          >Email</label
        >
        <input
          type="email"
          name="email"
          id="email"
          placeholder="Email"
          class="mt-1 border p-2 mb-2 rounded-md"
          required
        />
        <label for="phone" class="font-medium text-sm text-gray-500"
          >Phone</label
        >
        <input
          type="number"
          min="1"
          name="phone"
          id="phone"
          placeholder="Phone"
          class="mt-1 border p-2 mb-2 rounded-md"
          required
        />
        <label for="password" class="font-medium text-sm text-gray-500"
          >Password</label
        >
        <input
          type="password"
          name="password"
          id="password"
          placeholder="Password"
          class="mt-1 border p-2 mb-2 rounded-md"
          minlength="6"
          required
        />
        <label for="password2" class="font-medium text-sm text-gray-500"
          >Confirm Password</label
        >
        <input
          type="password"
          name="password2"
          id="password2"
          class="mt-1 border p-2 mb-2 rounded-md"
          placeholder="Confirm Password"
          minlength="6"
          required
        />
        <label for="gender" class="font-medium text-sm text-gray-500"
          >Gender</label
        >
        <select
          name="gender"
          class="mt-1 border p-2 mb-2 rounded-md"
          id="gender"
          selected="none"
          required
        >
          <option disabled selected value class="text-gray-200">
            -- select an option --
          </option>
          <option value="male">Male</option>
          <option value="female">Female</option>
          <option value="other">Other</option>
        </select>
        <div
          class="rounded-md flex w-full flex-row items-center justify-between mb-2"
        >
          <div class="flex flex-col w-1/3">
            <label for="day" class="block font-medium text-sm text-gray-500"
              >Day</label
            >
            <input
              type="text"
              id="day"
              name="day"
              class="mt-1 p-2 border rounded-md"
              placeholder="DD"
              maxlength="2"
            />
          </div>
          <div class="flex flex-col w-1/3 px-4">
            <label for="month" class="block font-medium text-sm text-gray-500"
              >Month</label
            >
            <input
              type="text"
              id="month"
              name="month"
              class="mt-1 p-2 border rounded-md"
              placeholder="MM"
              maxlength="2"
            />
          </div>

          <div class="flex flex-col w-1/3">
            <label for="year" class="block font-medium text-sm text-gray-500"
              >Year</label
            >
            <input
              type="text"
              id="year"
              name="year"
              class="mt-1 p-2 border rounded-md"
              placeholder="YYYY"
              maxlength="4"
            />
          </div>
        </div>
        <label class="block text-sm font-medium text-gray-500 mb-1"
          >Select Languages</label
        >

        <div class="space-y-1 mb-1">
          <div class="flex items-center">
            <input
              type="checkbox"
              id="english"
              name="languages[]"
              value="English"
              class="mr-2"
            />
            <label for="english">English</label>
          </div>

          <div class="flex items-center">
            <input
              type="checkbox"
              id="hindi"
              name="languages[]"
              value="Hindi"
              class="mr-2"
            />
            <label for="hindi">Hindi</label>
          </div>

          <div class="flex items-center">
            <input
              type="checkbox"
              id="tamil"
              name="languages[]"
              value="Tamil"
              class="mr-2"
            />
            <label for="tamil">Tamil</label>
          </div>

          <!-- Add more checkboxes as needed -->
        </div>
        <label for="address" class="font-medium text-sm text-gray-500"
          >Address</label
        >
        <textarea
          type="text"
          name="address"
          id="address"
          placeholder="Address"
          class="mt-1 border p-2 mb-2 rounded-md text-gray-800"
          required
        >
        </textarea>
        <button
          id="register"
          class="bg-gray-600 text-gray-100 rounded-md p-2 hover:bg-gray-500 mt-4"
          type="submit"
        >
          Register
        </button>
      </form>
    </div>
  </div>
</section>
