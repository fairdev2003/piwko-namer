<script lang="ts">
    export let cat_name: string = "s"

    let avatar: any, fileinput: any;
    
    const piwka_tesco = [
      "https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgbcnXmmxCa_5goHOmxdFF9-MYDW5STrY4c5RSET1REtAiPDqwf7nzD2DonpVp0FuPAg2YfafS0apsj8kM6r-A2KdkcyyT3V8Q0STAE6XVFeaL70Rs34WYA8YjnlpRpJDft2CfYy-_xTyE/s1600/DSC01397.JPG",
      "https://i.ytimg.com/vi/uroXoMnKdb4/maxresdefault.jpg",
      "https://i1.jbzd.com.pl/contents/2022/07/normal/5QvKKejg4vqVqhPfPDsoLWtyvchflRm2.jpg",
      "https://media.tenor.com/onZIFeyPLQoAAAAi/pivo-piwo.gif",
      "https://live.staticflickr.com/7303/14125444714_aee1e1600d_b.jpg",
      "https://avatars.akamai.steamstatic.com/99d99282e5c6743b24e05db09bcd416890ef0a22_full.jpg"
    ]
	
	const onFileSelected = (e: any) => {
        let image = e.target.files[0];
            let reader = new FileReader();
            reader.readAsDataURL(image);
            reader.onload = e => {
                avatar = e.target.result
            };
    }
</script>

<section class="mt-10 flex flex-col items-center justify-center ">
  <p class="font-bold text-2xl text-black cat-text w-full p-4">{cat_name}</p>
  <!-- svelte-ignore a11y-img-redundant-alt -->
    {#if avatar}
        <img
        src={avatar}
        alt="cat-photo"
        class="bg-cover bg-center w-[400px] h-[300px]"
        />
        {:else}
        <img
        src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgbcnXmmxCa_5goHOmxdFF9-MYDW5STrY4c5RSET1REtAiPDqwf7nzD2DonpVp0FuPAg2YfafS0apsj8kM6r-A2KdkcyyT3V8Q0STAE6XVFeaL70Rs34WYA8YjnlpRpJDft2CfYy-_xTyE/s1600/DSC01397.JPG"
        alt="cat-photo"
        class="bg-cover bg-center w-[400px] h-[300px]"
        />
    {/if}
  
  <button class="mt-5" on:click={()=>{fileinput.click();}}>Change piwko tesco image</button>
  <div class="flex flex-wrap w-[300px] gap-4">
    {#each piwka_tesco as piwko, value}
    <button class="mt-5" on:click={() => {
      avatar = piwko
    }}>Piwko tesco {value + 1}</button>
    {/each}
  </div>
  
  
  <input placeholder="Item" style="display:none" type="file" accept=".jpg, .jpeg, .png" on:change={(e)=>onFileSelected(e)} bind:this={fileinput} >
</section>

<style>
  .cat-text {
    animation-name: example;
    margin-top: 10px;
    animation-duration: 4s;
    animation-iteration-count: infinite;
  }

  @keyframes example {
    from {
      background-color: green;
    }
    to {
      background-color: yellow;
    }
  }
</style>
