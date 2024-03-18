<script lang="ts">
  import CatCard from './components/PiwkoCard.svelte';

  const name: string = true ? "Marcin" : "Bartosz"
  let cat_name: string = "Piwko tesco"

  $: {
    console.log("reloaded")
  }
</script>

<main>

  <div class="select-none">
    <h1 class="mb-5 font-medium">Piwko namer</h1>
    <p class="text-start mb-1">valuable piwko tesco name:</p>
    <input class="h-[50px] w-full text-lg flex justify-center text-center" type="text" placeholder="Type piwko tesco name here" bind:value={cat_name}/>
    <CatCard {cat_name}/>
  </div>
</main>

<style>
  
</style>
