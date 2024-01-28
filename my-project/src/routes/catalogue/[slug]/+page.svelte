<script>
  import { page } from "$app/stores";
  import Header from "$lib/components/Header.svelte";

  const books = {
    cse: [
      {
        id: 1,
        title: "Introduction to Algorithms",
        author:
          "Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein",
        price: 50.0,
        image_url: "https://upload.wikimedia.org/wikipedia/en/f/ff/Clrs4.jpeg",
      },
      {
        id: 2,
        title: "Clean Code: A Handbook of Agile Software Craftsmanship",
        author: "Robert C. Martin",
        price: 35.0,
        image_url:
          "https://m.media-amazon.com/images/I/41SH-SvWPxL.jpghttps://m.media-amazon.com/images/I/41SH-SvWPxL.jpg",
      },
    ],
    ece: [
      {
        id: 3,
        title: "Microelectronic Circuits",
        author: "Adel S. Sedra, Kenneth C. Smith",
        price: 45.0,
        image_url:
          "https://m.media-amazon.com/images/I/71JOrTLgVJL._AC_UF1000,1000_QL80_.jpg",
      },
      {
        id: 4,
        title: "Communication Systems",
        author: "Simon Haykin, Michael Moher",
        price: 40.0,
        image_url:
          "https://m.media-amazon.com/images/I/51bh+pgU9bL._AC_UF1000,1000_QL80_.jpg",
      },
    ],
    eee: [
      {
        id: 5,
        title: "Electric Machinery Fundamentals",
        author: "Stephen J. Chapman",
        price: 55.0,
        image_url:
          "https://m.media-amazon.com/images/I/51TCtU2N4oL._AC_UF1000,1000_QL80_.jpg",
      },
      {
        id: 6,
        title: "Power System Analysis and Design",
        author: "J. Duncan Glover, Thomas Overbye, Mulukutla S. Sarma",
        price: 48.0,
        image_url:
          "https://m.media-amazon.com/images/I/61U+KikllTL._AC_UF1000,1000_QL80_.jpg",
      },
    ],
    civil: [
      {
        id: 7,
        title: "Structural Analysis",
        author: "Russell C. Hibbeler",
        price: 42.0,
        image_url:
          "https://m.media-amazon.com/images/I/71cQ2J0WCHL._AC_UF1000,1000_QL80_.jpg",
      },
      {
        id: 8,
        title: "Geotechnical Engineering: Principles and Practices",
        author: "Donald P. Coduto, Man-chu Ronald Yeung, William A. Kitch",
        price: 50.0,
        image_url:
          "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRwamV35sETKvZYc9sNDX-Qp3rkzw-wGu9_kJxCJwA8rNGW3xiAmfFuZC4vD3-1SDW1NHA&usqp=CAU",
      },
    ],
  };

  $: content = books[$page.params.slug] ?? books["cse"];
</script>

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
    <div class="w-5/6 p-12 flex flex-col">
      {#each content as item}
        <div class="flex flex-row space-x-12 py-2 items-start justify-center">
          <div class="w-1/6">
            <img src={item.image_url} alt={item.title} />
          </div>
          <div class="flex flex-col w-3/6">
            <div class="text-2xl font-bold">{item.title}</div>
            <div class="text-xl">{item.author}</div>
          </div>
          <div class="flex flex-col w-1/6">
            <div class="text-xl">${item.price}</div>
          </div>
          <div class="flex flex-col w-1/6">
            <button class="bg-yellow-500 rounded-md py-2">Add to Cart</button>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>
