<script lang="ts">
  import axios from 'axios'
  import { onMount } from 'svelte';

  let text: string = ''
  let data: any = []

  let letter: string[] = ["a", "b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "n", "m"]

  const number_of_products: number = 10

  const increment = () => {
    const index = Math.floor((Math.random() * letter.length));

    text = text + letter[index]
  }
  onMount(
      async () => {
        data = await axios.get("https://dummyjson.com/products")
        console.log(data.data)
      }
    )
</script>

<button on:click={increment}>
  Add random letter
</button>
<p>Data from API:</p>



<p>{ text.length }</p>
<input bind:value={text} on:change={() => {
  console.log(text)
}}/>


<style>
  
</style>
