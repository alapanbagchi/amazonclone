<script>

    export let logo
    export let slogan
</script>


    <div class="content">
        <img src="assets/Hero/Amazon Fire.png" alt="">
        <div class="info">
            <div class="logo">
                <img class="itemlogo" src={logo} alt="Fire Stick Logo">
            </div>
            <div class="slogan">
                <p>{slogan}</p>
            </div>
            <div class="cta">
                <a class="cta-btn" href="/">Shop Now</a>
            </div>
        </div>
    </div>


<style>

    .content
    {
        width: 91vw;
        display: grid;
        grid-template-columns: 1fr  1fr;
        justify-items: center;
        align-items: center;
    }
    .info
    {
        width: 100%;
        height:40%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 50px;
    }
    .logo
    {
        width: 100%;
        height:62px;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .itemlogo
    {
        width: 25vw !important;
        object-fit: cover;
    }
    .content img
    {
        object-fit: contain;
        width:40vw;
    }
    .slogan
    {
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        font-weight: 600;
        font-size: 1.1em;
    }
    .cta
    {
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        font-weight: 600;
    }
    .cta-btn
    {
        padding:15px 30px 15px 30px;
        border-radius: 5px;
        background: var(--amazon-yellow);
        color:white;
    }
</style>