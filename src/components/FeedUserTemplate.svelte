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


</script>
    <div class="feeduser" style='padding-top:{padding}'>
    <div class="recentItems">
        <Poster {posterImage} {posterSlogan} {posterTitle} />
    </div>
    <div class="subnav">
        <SubNav navItems={navItems} on:current={filterproducts}/>
    </div>
    <div class="products">
        
        <div id="product-wrapper" class="product-wrapper">
            
            {#each products as product,i}
            {#if product.section==selected}
            <div id="container" class="container pointer">
                <Products  name={product.name} companyName={product.companyName} image={product.image} price={product.price} color={product.color} />
            </div>
            {/if}
            {/each}
            
        </div>
        <div class="ctacontainer">
            <div class="showmore">
                <a class="cta" style="color:#ffffff" href="/">Show More</a>
            </div>
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
            border-top: 1px solid #e8e8e8;
            border-bottom: 1px solid #e8e8e8;

        }
        
        .showmore
        {
            padding: 15px 30px 15px 30px;
            background: var(--amazon-blue);
            color:white;
            display: flex;
            justify-content: center;
            width: 150px;
        }
        .ctacontainer
        {
            width: 100%;  
            display: flex;
            justify-content: center;  
            color: white;
            padding-top: 50px;
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
            height:fit-content;
            height:fit-content;
            display: flex;
            justify-content: center;
            flex-direction: column;
        }
        .product-wrapper
        {
            width: 100%;
            display: grid;
            grid-template-columns: 1fr 1fr 1fr 1fr;

        }
      
        @media only screen and (max-width:1100px)
        {
            .subnav
            {
                padding:0;
            }
        }
    </style>
