<script>

export let show_categories = false

if(screen.width<800)
{
    show_categories=true
}
    const categories=[
    {
        name:'Fresh',
        image:'./assets/categories/fresh.png'
    },
    {
        name:'Echo',
        image:'./assets/categories/echo.png'
    },
    {
        name:'Food',
        image:'./assets/categories/food.png'
    },
    {
        name:'Electronics',
        image:'./assets/categories/laptop.png'
    },
    {
        name:'Fashion',
        image:'./assets/categories/fashion.png'
    },
    {
        name:'Home',
        image:'./assets/categories/home.png'
    },
    {
        name:'Sports',
        image:'./assets/categories/sports.png'
    },
    {
        name:'Toys',
        image:'./assets/categories/toys.png'
    },
    {
        name:'Beauty',
        image:'./assets/categories/beauty.png'
    },
]



</script>



<div class="category-wrapper {show_categories===true?'':'hidden'}">

    <div class="category">

        {#each categories as category}
        <div class="items pointer">
            <div class="image">
                <img src={category.image} alt=''>
            </div>
            <div class="text">
                <p>{category.name}</p>
            </div>
            
        </div>
       {/each}
    </div>

</div>


<style>
    .category-wrapper
    {
        width: 100%;
        height: 200px;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .hidden
    {
        display:none;
    }
    .category
    {
        width: 82%;
        height:100%;
        display: flex;
        gap: 80px;
        justify-content: center;
        align-items: center;
    }
    .items
    {
        width: 140px;
        height: 120px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap:10px;
    }
    .image
    {
        width: 100%;
        height: 80px;
    }
    .image img
    {
        width: 100%;
        height: 100%;
        object-fit: contain;
    }
    .text
    {
        
        font-weight: 500;
        color:var(--text-primary)
    }
    @media only screen and (max-width:800px)
    {
        .category-wrapper
        {
            height: 45px;
            background: #e2e2e2;
            margin-top: -6px;
        }
        .category
        {
            width:100%;
            overflow-x: scroll;
            overflow-y: hidden;
            gap: 40px;
            display: flex;
            justify-content:space-between;
            padding-left: 12%;
        }
        .items
        {
            width: 100%;
            height: 100%;
        }
        .image
        {
            display: none;
        }
        ::-webkit-scrollbar 
        {
            display: none;
        }
    }
</style>