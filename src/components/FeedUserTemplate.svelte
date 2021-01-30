<script>
import Poster from "./Poster.svelte";
import Products from "./Products.svelte";
import SubNav from "./SubNav.svelte";
export let posterImage
export let posterTitle
export let posterSlogan
export let products
export let navItems
export let index
let padding
if(index==0)
{
    padding = '25vh';
}
$: selected=navItems[0]

const filterproducts = (event) =>
{   
    selected = event.detail.selected
} 
$: translate = 0

$: count=0
const prev = () =>
{
    let prev = setInterval(()=>
        {
            translate++;
            [...document.getElementsByClassName('container')].forEach((element)=>{element.style.transform=`translateX(${translate}px)`})
            if(translate==document.getElementById('product-wrapper').offsetWidth-151)
            {
                clearInterval(prev)
            }
        },0.001)
        count--;
}
    


const next = () =>
{
    let next = setInterval(()=>
        {
            translate++;
            console.log(document.getElementById('product-wrapper').offsetWidth);
            [...document.getElementsByClassName('container')].forEach((element)=>{element.style.transform=`translateX(-${translate}px)`})
            if(translate==document.getElementById('product-wrapper').offsetWidth-151)
            {
                clearInterval(next)
            }
        
        },0.001)
        count++;
}


</script>
    <div class="feeduser" style='padding-top:{padding}'>
    <div class="recentItems">
        <Poster {posterImage} {posterSlogan} {posterTitle} />
    </div>
    <div class="subnav">
        <SubNav navItems={navItems} on:current={filterproducts}/>
    </div>
    <div class="products">
        <div on:click={prev} class="prev pointer">
            <img width="20px" height="20px" src="./assets/left-arrow.svg" alt="">
        </div>
        <div id="product-wrapper" class="product-wrapper">
            
            {#each products as product,i}
            {#if product.section==selected}
            <div id="container" class="container pointer">
                <Products  name={product.name} companyName={product.companyName} image={product.image} price={product.price} color={product.color} />
            </div>
            {/if}
            {/each}
            
        </div>
        <div on:click={next} class="next pointer">
            <img width="20px" height="20px" src="./assets/right-arrow.svg" alt="">
        </div>
    </div>
    </div>
    
    <style>
        .container
        {
            min-width: 400px;
            min-height: 460px;
            background: #ffffff;
            display: flex;
            justify-content: center;
            align-items: center;
            border-right: 1px solid #e8e8e8;

        }
        .next
        {
            width: 70px;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #F6F6F6;
            cursor:pointer;
        }
        .prev
        {
            width: 70px;
            height: 100%;
            display: flex;
            justify-content: center;
            background: #F6F6F6;
            align-items: center;
            cursor:pointer;
        }
        .feeduser
        {
            width: 100%;
            min-height: 100vh;
            background: #F6F6F6;
            padding-bottom: 25vh;
        }
        .feeduser:nth-child(0)
        {
            display: none;
        }
        .recentItems
        {
            width: 100%;
            min-height: fit-content;

            display: flex;
            justify-content: center;
        }
        .subnav
        {
            padding-top: 4em;
            padding-bottom: 4em;
        }
        .products
        {
            width: 100%;
            height:460px;
            display: flex;
            justify-content: center;
            
        }
        .product-wrapper
        {
            width: 100%;
            display: flex;
            overflow:hidden;

        }
      
        @media only screen and (max-width:1100px)
        {
            .subnav
            {
                padding:0;
            }
        }
    </style>
