<script>
    
    import { valI } from "../stores/data";
    import { valO, flag } from "../stores/outputData";

    const palindrome = ()=>{
        var i=0
        var j=$valI.length-1;
        var f = 1;
        while(i < j)         // 12354321
        {
            if($valI[i] != $valI[j])
            {
                f = 0;
                break;
            }
            i++;
            j--;
        }

        if(f == 0)
            valO.set("FALSE");
        
        else
            valO.set("TRUE");
        flag.set(1);
    }

</script>

<main class="relative">


    <div class="items-center w-96 bg-teal-700" style="height: 250px;">
        <!-- heading -->
        <p class="font-bold text-white text-center">Number Palindrom Checker</p>
        
        <br>
        
        <!-- OPERATION -->
        <div class="bg-teal-700 w-96 mx-auto p-1">

            <div class="flex text-white justify-evenly">
                <button class="border rounded p-1 hover:bg-teal-800" on:click={palindrome}>Check Palindrome</button>
            </div>
        </div>
    </div>  
</main>