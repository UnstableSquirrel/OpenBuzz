<script>

  import Router from "svelte-spa-router"
  import OpenBuzz from "./routes/OpenBuzz.svelte"
  import MainBuzz from "./routes/MainBuzz.svelte"
  import OpenBuzzDogira from "./routes/OpenBuzzDogira.svelte"

  let routes = {
    "/": OpenBuzz,
    "/MainBuzzBoard": MainBuzz,
    "/OpenBuzzDogira": OpenBuzzDogira,
    
  }

  let lastUrl = location.href
  new MutationObserver(() => {
    const url = location.href
    if (url !== lastUrl) {
      lastUrl = url
      onUrlChange()
    }
  }).observe(document, {subtree: true, childList: true})
 
 
  function onUrlChange() {
    location.reload()
  }

</script>

<main>

  <Router {routes}/>

  <!-- <header>

    <nav>
      <a href="#/">Home</a>
      <a href="#/Test">BuzzBoard</a>
    </nav>

  </header> -->

</main>

<style>
</style>
