<script>

export let footer;
let contents=footer.content
</script>

<div class="footer_wrapper">
    <div class="sub_footer">
    {#each footer as item}
        <div class="table1">
            <p>{item.name}</p>
            <div class="content">
                {#each item.content as content}
                    <p>{content}</p>
                {/each}
            </div>
        </div>
    {/each}
    </div>
    <div class="main_footer">

        <div class="info">
            <img src="./Assets/amazonlogo.png" alt="">
            <p>C 1996-2021</p>
            <p>Conditions of Use and Sale</p>
            <p>Privacy Notice</p>
        </div>

    </div>
</div>

<style>
    .footer_wrapper
    {
        width: 100%;
        height: 90vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    .sub_footer
    {
        width:80%;
        height: 90%;
        display: grid;
        grid-template-columns: repeat(5,1fr);
        border-bottom: 1px solid #d6d6d6;
        margin-top: 20vh;
    }
    .table1
    {
        width:100%;
        height: 100%;
        display: flex;
        flex-direction: column;
    }
    .table1 > p
    {
        font-weight: 700;
        color:var(--text-primary)
    }
    .content
    {
        margin-top: 1em;
        font-weight: 400;
        color:var(--text-secondary)
    }
    .content p
    {
        margin-top: 1.5em;
        cursor: pointer;
    }
    .main_footer
    {
        width:80%;
        height:20%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .info
    {
        display:flex;
        gap: 50px;
        font-weight: 400;
        color: var(--text-secondary);
    }
    .info p
    {
        cursor:pointer;
    }
    .info img
    {
        width:100px;
    }
</style>