<script>

    import {createEventDispatcher} from 'svelte'
    const dispatch = createEventDispatcher();
    export let navItems
    $: current=navItems[0]

</script>

<div class="subnav">
    <ul>
        {#each navItems as data,i}
            <li on:click={()=>{current=navItems[i];dispatch('current',{'selected':current})} } class="pointer {current===navItems[i]?'active':''}">{navItems[i]}</li>
        {/each}
        
        
    </ul>
</div>

<style>
    .subnav
    {
        width:100%;
        height:50px;

    }
    ul
    {
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        gap:50px;
        font-weight: 500;
        color:var(--text-secondary);
    }
    .active
    {
        color: var(--text-primary);
        border-bottom: 3px solid var(--amazon-yellow);
        padding-bottom: 5px;
    }
    @media only screen and (max-width:800px)
    {
        .subnav
        {
            margin-top: 10px;
            height: 45px;
            padding-right: 4%;
            padding-left: 4%;
        }
        ul
        {
            width:100%;
            overflow-x: scroll;
            overflow-y: hidden;
            gap: 40px;
            display: flex;
            justify-content:space-between;
        }
        li
        {
            white-space: nowrap;
            width: 100%;
            height: fit-content;
            padding-bottom: 2px;
        }

        ::-webkit-scrollbar 
        {
            display: none;
        }
        .active
        {
            padding-bottom: 2px;
        }
    }
</style>