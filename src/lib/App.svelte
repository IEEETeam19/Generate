<script>

  import {valI} from "../stores/data.js";
  import {valO, flag} from "../stores/outputData.js";
  import Box2 from "./PowerOf10.svelte";
  import { each } from "svelte/internal";
    import PowerOf2 from "./PowerOf2.svelte";
    import PowerOf10 from "./PowerOf10.svelte";
  // import Route1 from "../routes/route1.svelte";

  // let arr = []; 
  export let a2;
  a2 = $valO;
  var inpValue;
  // var l = []; 
  
  const num = (event)=>{
    if(event.keyCode === 13)
    {
      inpValue = event.target.value;
    }
  }
  
  // '349', '349\n3', '349\n3\n8', '349\n3\n8\n4', '349\n3\n8\n4\n89'
  
  const inputTake = function NL()
  {

      valI.set(inpValue);
      console.log($valI);
  }

   
</script>

<main class="app">

  <!-- <div></div> -->
<h2 class="font-bold text-center text-teal-900 text-lg">ONLINE NUMBER TOOLS</h2>
<p class="text-center text-sm m-1"> <span class="bg-black text-teal-400 rounded px-1">True Or False Calculator</span> Choose from the following</p>

<div class="bg-black w-full h-96 my-5">
  <div class="text-white"> 
    </div>
    <div class="flex center-contents justify-evenly">
        <!-- <div class="text-teal-700 mx-20 text-center my-4">
            <p class="font-bold">INPUT</p>
            
            <textarea style="resize: none;" class="text-white bg-teal-600 w-96 h-72" name="" id="t1" cols="30" rows="10" on:keydown={num}></textarea>
            <div>
              <button on:click={inputTake} class="bg-teal-700 text-white rounded border-2 m-1 p-1 hover:bg-teal-900">SUBMIT</button>
            </div>
        </div> -->
        <div class="text-teal-700 mx-20 text-center my-4">
            <p class="font-bold">OUTPUT</p>
            <div class="bg-teal-600 w-96 h-72 text-white" id="Op">
              {#if $flag == 1}
                {#each $valO as ele}
                  <ul>{ele}</ul>
                {/each}
              {/if}
          </div>
        </div>
    </div>
</div>

  <div class="flex content-center mx-3 justify-evenly">
    <!-- <Box1/> -->
    <PowerOf2/>
    <PowerOf10/>
    <!-- <Box3/> -->
  </div>
  <div class="text-center text-teal-800 font-bold">
    <a href="https://www.google.com/">
      HOME
     </a>
  </div>
</main>