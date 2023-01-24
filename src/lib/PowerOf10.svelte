<script>

    import {valI} from "../stores/data.js"
    import {valO, flag} from "../stores/outputData.js"
    
    var flagD = 0;
    var arr = [];

    var nums = ()=>
    {   
        console.log("Entered value: "+$valI);
        arr = [];
        for(var i=0; i<$valI; i++)
        {
            arr = [...arr, Math.pow(10, i)];
        }
        valO.set(arr);
        console.log($valO);
        flag.set(1);
    }

    var dec = ()=>
    {
        flagD=1;
        arr.reverse();
        valO.set(arr);
    }
</script>

<main>
    <div class="bg-teal-700 text-white w-96 px-1" style="height: 250px;">
        <p class="font-bold text-lg text-center">POWER OF 10</p>
        <div class="flex content-center justify-between">
            <div class="op1">
                <p class="text-lg bold">Length</p>
                
            <label for="s1">
                <input type="text" class="border rounded bg-teal-900 ml-2 w-20" bind:value={$valI}>
                <p class="text-xs">Generate this many powers of 10</p>
            </label>
            <button class="text-xs border rounded px-1 content-center hover:bg-teal-900" on:click={nums}>SUBMIT</button>
            </div>

            <div class="op2">
                <p class="text-lg bold text-center">Order of Series</p>
                <label for="r1">
                    <!-- <span>

                    </span> -->
                    <input type="radio" class="border rounded bg-teal-900 w-20" name="ord" on:change={nums}>
                    <!-- <p class="text-xs">Increasing Order</p> -->
                    <span>
                        Increasing Order
                    </span>
                    
                </label>
                <label for="r2">
                    <input type="radio" class="border rounded bg-teal-900 w-20" name="ord" on:change={dec}>
                    <!-- <p class="text-xs"></p> -->
                    <span>
                        Decreasing Order
                    </span>
                </label>
            </div>
        </div>
    </div>
</main>