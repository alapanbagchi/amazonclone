<script>
import Hero from "./Hero.svelte";

$: dist = 0
let count = 0
const sliders = [
    {
        logo:'./Assets/Hero/Fire Stick.png',
        slogan:'Telivision Redefined'
    },
    {
        logo:'./Assets/Hero/Fire Stick.png',
        slogan:'Telivision Redefined'
    },
    {
        logo:'./Assets/Hero/Fire Stick.png',
        slogan:'Telivision Redefined'
    },
    {
        logo:'./Assets/Hero/Fire Stick.png',
        slogan:'Telivision Redefined'
    },
]


const nextSlide = () =>
{
    if(count<sliders.length-1)
    {
        let forward = setInterval(()=>
        {
            dist++;
            [...document.getElementsByClassName('hero_wrapper')].forEach(element =>element.style.right=`${dist}vw`)
            if(dist==count*91)
            {
                clearInterval(forward)
            }
        },0.15)
        count++
    }
    
}
const prevSlide = () =>
{

    if(count!=0)
    {
        let previous = setInterval(()=>
        {
            dist--;
            [...document.getElementsByClassName('hero_wrapper')].forEach(element =>element.style.right=`${dist}vw`)
            if(dist==count*91)
            {
                clearInterval(previous)
            }
        },0.15)
        count--
    }
    
}

</script>
<div class="hero">

    <div on:click={prevSlide} class="prev pointer">
        <img width="40px" alt="" src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiPjxwYXRoIGQ9Ik0yMCAuNzU1bC0xNC4zNzQgMTEuMjQ1IDE0LjM3NCAxMS4yMTktLjYxOS43ODEtMTUuMzgxLTEyIDE1LjM5MS0xMiAuNjA5Ljc1NXoiLz48L3N2Zz4=">
    </div>
    <div class="slide_content">
    {#each sliders as slider}
    <div id="hero_wrapper" class="hero_wrapper">
            <Hero logo={slider.logo} slogan={slider.slogan} />
    </div>
    {/each}

  
    </div>
    <div on:click={nextSlide} class="next pointer">
        <img alt="" width="40px" src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiPjxwYXRoIGQ9Ik00IC43NTVsMTQuMzc0IDExLjI0NS0xNC4zNzQgMTEuMjE5LjYxOS43ODEgMTUuMzgxLTEyLTE1LjM5MS0xMi0uNjA5Ljc1NXoiLz48L3N2Zz4=">
    </div>
</div>

<style>
    .hero_wrapper
    {
        width:100vw;
        height:75vh;
        display: flex;
        justify-content: center;
        position: relative;
    }
    .hero
    {
        width:100%;
        height: calc(100vh - 250px);
        display: grid;
        grid-template-columns:0.11fr 1fr 0.11fr;
        
    }
    .prev
    {
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: flex-end;
        align-items: center;
    }
    .next
    {
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: flex-start;
        align-items: center;
    }
    .slide_content
    {
        position: relative;
        display: flex;
        width:100%;
        overflow: hidden;
    }


</style>