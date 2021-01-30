<div class="userdata">
    <div class="greetings">
        <p>Hello, Alapan Bagchi</p>
    </div>
    <div class="redirect_options">
        <p class="pointer">Prime</p>
        <p class="pointer">Fresh</p>
        <p class="pointer">Video</p>
        <p class="pointer">Music</p>
    </div>
</div>

<style>
    .userdata
    {
        width:100%;
        height:80px;
        background:var(--amazon-blue);
        color:var(--white-text);
        display: grid;
        grid-template-columns: 2fr 0.8fr;
        margin-top:5px;
        font-weight: 500;
    }
    .greetings
    {
        display: flex;
        align-items: center;
        padding-left: 11.5%;
        font-weight: 500;
    }
    .redirect_options
    {
        display: flex;
        align-items: center;
        gap: 40px;
    }
    @media only screen and (max-width:800px)
    {
    .userdata
    {
        display: none;
    }
    }
</style>