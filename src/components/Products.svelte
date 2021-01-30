<script>
    export let name;
    export let companyName;
    export let image;
    export let color;
    export let price;

    $: current=color[0]
    $: active = color[0]
    $: y = 0

    


</script>




    <div class="item">
        <div class="image">
            <img src={image} alt="">
        </div>
        <div class="colors">
            {#each color as colors,i}
            <div on:click={()=>active = colors} class="{active===colors?'active':''}">
                <div class="color" style="background-color:{colors}">

                </div>
            </div>

            {/each}
        </div>
        <div class="nameandprice">
        <div class="name">
            <p>{name} by <span class="company_name">{companyName}</span></p>
        </div>
        <div class="price">
            <p>{price}</p>
        </div>
        </div>
    </div>

<style>


.item
{
   
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap:20px;
}
.image
{
    width:200px;
    height:222.5px;
    flex:0.6;
}
.image img
{
    width: 100%;
    height:100%;
    object-fit: contain;
}
.nameandprice
{
    display: flex;
    flex-direction: column;
    gap:20px;
    flex:0.01;
}
.colors
{
    width:100%;
    display: flex;
    justify-content:center;
    gap: 20px;
    margin:20px 0;
    flex:0.2;
}
.active
{
    width: 24px;
    height:24px;
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px solid black;
    border-radius: 80px;

}
.color
{
    width:20px;
    height: 20px;
    border-radius: 80px;
}
.name
{
    width:100%;
    display: flex;
    justify-content:center;
    color:var(--text-primary);
    font-weight: 600;
}
.company_name
{
    color:var(--text-secondary);

}
.price
{
    width:100%;
    display: flex;
    justify-content:center;
    font-weight: 500;
    color:var(--text-primary)
}
</style>