<script>
  import { page } from "$app/stores";
  import Header from "$lib/components/Header.svelte";

  const books = [
    {
      id: 1,
      title: "Introduction to Algorithms",
      author:
        "Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein",
      price: 50.0,
      amount: 1,
      image_url: "https://upload.wikimedia.org/wikipedia/en/f/ff/Clrs4.jpeg",
    },
    {
      id: 2,
      title: "Clean Code: A Handbook of Agile Software Craftsmanship",
      author: "Robert C. Martin",
      price: 35.0,
      amount: 3,
      image_url:
        "https://m.media-amazon.com/images/I/41SH-SvWPxL.jpghttps://m.media-amazon.com/images/I/41SH-SvWPxL.jpg",
    },

    {
      id: 3,
      title: "Microelectronic Circuits",
      author: "Adel S. Sedra, Kenneth C. Smith",
      price: 45.0,
      amount: 2,
      image_url:
        "https://m.media-amazon.com/images/I/71JOrTLgVJL._AC_UF1000,1000_QL80_.jpg",
    },
    {
      id: 4,
      title: "Communication Systems",
      author: "Simon Haykin, Michael Moher",
      price: 40.0,
      amount: 1,
      image_url:
        "https://m.media-amazon.com/images/I/51bh+pgU9bL._AC_UF1000,1000_QL80_.jpg",
    },
  ];
</script>

<section class="h-full">
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
    <div class="w-5/6 p-12 flex flex-col">
      <h2 class="text-2xl">Cart</h2>
      <div class="flex flex-row space-x-12 py-2 items-start justify-center">
        <div class="flex flex-col text-xl w-3/6">Book</div>
        <div class="flex flex-col w-1/6">
          <div class="text-xl">Price</div>
        </div>
        <div class="flex flex-col w-1/6">
          <div class="text-xl">Quantity</div>
        </div>
        <div class="flex flex-col w-1/6">
          <div class="text-xl">Amount</div>
        </div>
      </div>
      {#each books as item}
        <div class="flex flex-row space-x-12 py-2 items-start justify-center">
          <div class="w-1/6">
            <img src={item.image_url} alt={item.title} />
          </div>
          <div class="flex flex-col w-2/6">
            <div class="text-lg font-bold">{item.title}</div>
            <div class="text-md">{item.author}</div>
          </div>
          <div class="flex flex-col w-1/6">
            <div class="text-lg">${item.price}</div>
          </div>
          <div class="flex flex-col w-1/6">
            <div class="text-lg">{item.amount}</div>
          </div>
          <div class="flex flex-col w-1/6">
            <div class="text-lg">${item.price * item.amount}</div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>
