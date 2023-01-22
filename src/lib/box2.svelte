<script>

    import {valI} from "../stores/data.js"
    import {valO, flag} from "../stores/outputData.js"
    
    const prime = ()=>
    {
        var num = parseInt($valI, 10);
        console.log(typeof(num));
        let isPrime = true;
        valO.set("FALSE");
        flag.set(0);

        if(num == 1)
            valO.set("TRUE");
        else if(num > 1)
        {
            for(let i=2; i<num; i++)
            {
                if(num % i == 0)
                {
                    isPrime = false;
                    break;
                }
            }
            if(isPrime)
                valO.set("TRUE");
            else
                valO.set("FALSE");
        }

        flag.set(1);
        console.log(num+" is prime: "+$valO);       
    }

    const composite = ()=>
    {
        var num = parseInt($valI, 10);
        console.log(typeof(num));
        let isPrime = true;
        valO.set("FALSE");
        flag.set(0);

        if(num == 1)
            valO.set("FALSE");
        else if(num > 1)
        {
            for(let i=2; i<num; i++)
            {
                if(num % i == 0)
                {
                    isPrime = false;
                    break;
                }
            }
            if(isPrime)
                valO.set("FALSE");
            else
                valO.set("TRUE");
        }

        flag.set(1);
    }

</script>

<main>
    <div class="bg-teal-700 text-white w-96 px-1" style="height: 250px;">
        <p class="text-center font-bold">Primality Test</p>
        <br>

        <label for="oprn" class="text-white">
            <input type="radio" name="oprI" id="" on:change={prime}>
                Report status of Prime Number
                <p class="text-xs">It reports whether the given number is 
                    prime or not
                </p>
        </label>

        <br>

        <label for="oprn" class="text-white">
            <input type="radio" name="oprI" id="" on:change={composite}>
            Report status of Composite Number
                <p class="text-xs">It reports whether the given number is 
                    prime or not
                </p>
        </label>

    </div>
</main>