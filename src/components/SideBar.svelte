<script>
  import Profile from "./Profile.svelte";
  import Stories from "./Stories.svelte";
  import Footer from "./Footer.svelte";
</script>

<style>
  .SideBar {
    position: relative;
    padding: 4.5em 0 0 0;
  }
  .SideBar-container {
    position: fixed;
  }
</style>

<div class="SideBar">
  <div class="SideBar-container">
    <Profile />
    <Stories />
    <Footer />
  </div>
</div>
