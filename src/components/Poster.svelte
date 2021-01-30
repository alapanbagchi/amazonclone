<script>
    export let posterImage
    export let posterTitle
    export let posterSlogan
</script>


<div class="recentitems">
    <div class="image">
        <img src="{posterImage}" alt={posterTitle}>
    </div>
    <div class="text">
        <h1>{posterTitle}</h1>
        <div class="description">
            <span class="border"></span>
            <p>{posterSlogan}</p>
        </div>

    </div>
</div>

<style>
    .recentitems
    {
        width:80%;
        height: fit-content;
        display: grid;
        grid-template-columns: 1fr 1fr;
        column-gap:11%;
        background: #ffffff;
    }
    .image
    {
        background: linear-gradient(
                    90deg, #ffffff 21px, transparent 1%) center, linear-gradient(#ffffff 21px, transparent 1%) center, #232f3e;
        background-size: 22px 22px;

    }
    .image img
    {
        width: 34.65vw;
        height: 25vw;
        position: relative;
        top:-50px;
        left:50px;
    }
    .text
    {
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        flex-direction: column;        
    }
    .text h1
    {
        font-size: clamp(1rem, 2.5vw, 1.5rem); 
        margin-bottom: 2em;
    }
    .text p
    {
        width: 45%;
        font-weight: 500;
        color:var(--text-secondary);
    }
    .description
    {
        display: grid;
        grid-template-columns: 0.01fr 1fr;
        line-height: 30px;
        column-gap:30px ;
        margin-bottom: 2em;
    }
    .border
    {
        width: 40%;
        height: 100%;
        background:var(--amazon-yellow);
    }
    @media only screen and (max-width:1100px)
    {
        .text h1
        {
            font-size: 1.2em;
        }
        .recentitems
        {
            width: 100%;
            height: 60vh;
            grid-template-columns: none;
            grid-template-rows:1fr 1fr;
            background:#F6F6F6;
        }
        .image
        {
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }
        .image img
        {
            width: 100%;
            height: 100%;
            position: relative;
            object-fit: cover;
            top: 0;
            left: 0;
        }
        .text
        {
            display: flex;
            justify-content: center;
            text-align: center;
        }
        .border
        {
            display: none;
        }
        .description
        {
            grid-template-columns: none;
        }
        .text h1
        {
            margin-top: 2em;
            margin-bottom: 2em;
        }
        .description
        {
            display: flex;
            justify-content: center;
        }
        .text p
        {
 
            width:80%;
        }
        
    }   
</style>