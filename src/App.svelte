<script>
  // Se utliza onMount para hacer peticiones HTTP
  import { onMount } from "svelte";
  import Header from "./components/Header.svelte";
  import Main from "./components/Main.svelte";
  import TimeLine from "./components/TimeLine.svelte";
  import SideBar from "./components/SideBar.svelte";

  let data = {};
  const API = "https://us-central1-pugstagram-co.cloudfunctions.net/data";
  onMount(async () => {
    const response = await fetch(API);
    data = await response.json();
  });
</script>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Lato:wght@400;700;900&display=swap");
  @import url("https://fonts.googleapis.com/css2?family=Pacifico&display=swap");
  :global(body) {
    background-color: #fafafa;
    color: rgba(38, 38, 38, 0.7);
    font-family: "Lato", sans-serif;
    margin: 0;
    padding: 0;
  }
  :global(h1, h2, h3) {
    margin: 0;
    padding: 0;
  }
</style>

<Header />
<Main>
  <!-- Datos que provienen de la petición onMount -->
  <TimeLine posts={data.posts} />
  <SideBar />
</Main>
