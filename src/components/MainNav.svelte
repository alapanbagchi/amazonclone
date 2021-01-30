<script>

import {createEventDispatcher} from 'svelte'
const dispatch = createEventDispatcher()

let rot=180
const toggleMenu=()=>
{
    dispatch('category_toggle')
    document.getElementById('dropdown-icon').style.transform = `rotate(${rot}deg)`
    rot+=180
}
let searchicon='000000';
if(screen.width<801)
    searchicon='ffffff'
</script>

<header>
    <nav>
        <ul>
            <div class="logoandcategory">

                <div class="logo">
                    <img class="pointer" width="35px" src="./assets/logo.png" alt="Amazon Logo">
                </div>
                <div class="options">
                    <p>Orders</p>
                    <p >Sign In</p>
                    <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3Cpath d='M10 19.5c0 .829-.672 1.5-1.5 1.5s-1.5-.671-1.5-1.5c0-.828.672-1.5 1.5-1.5s1.5.672 1.5 1.5zm3.5-1.5c-.828 0-1.5.671-1.5 1.5s.672 1.5 1.5 1.5 1.5-.671 1.5-1.5c0-.828-.672-1.5-1.5-1.5zm6.305-15l-3.432 12h-10.428l-3.777-9h-2.168l4.615 11h13.239l3.474-12h1.929l.743-2h-4.195z'/%3E%3C/svg%3E" alt="">

                </div>
                <div on:click={toggleMenu} class="category pointer">
                    <p>Home</p>
                    <img id="dropdown-icon" width="7px" src="assets/dropdown.svg" alt="dropdown icon">
                </div>
            </div>
            <div class="search">
                <div class="items">
                    <img width="15px" src="data:image/svg+xml,%3Csvg fill='%23{searchicon}' width='24' height='24' xmlns='http://www.w3.org/2000/svg' fill-rule='evenodd' clip-rule='evenodd'%3E%3Cpath d='M15.853 16.56c-1.683 1.517-3.911 2.44-6.353 2.44-5.243 0-9.5-4.257-9.5-9.5s4.257-9.5 9.5-9.5 9.5 4.257 9.5 9.5c0 2.442-.923 4.67-2.44 6.353l7.44 7.44-.707.707-7.44-7.44zm-6.353-15.56c4.691 0 8.5 3.809 8.5 8.5s-3.809 8.5-8.5 8.5-8.5-3.809-8.5-8.5 3.809-8.5 8.5-8.5z'/%3E%3C/svg%3E" alt="">
                    <input type="text" placeholder="Search For Anything">
                </div>
            </div>

            <div class="return_cart_icon">
                <p>Orders</p>
                    <p class="signin">Sign In</p>
                    <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3Cpath d='M10 19.5c0 .829-.672 1.5-1.5 1.5s-1.5-.671-1.5-1.5c0-.828.672-1.5 1.5-1.5s1.5.672 1.5 1.5zm3.5-1.5c-.828 0-1.5.671-1.5 1.5s.672 1.5 1.5 1.5 1.5-.671 1.5-1.5c0-.828-.672-1.5-1.5-1.5zm6.305-15l-3.432 12h-10.428l-3.777-9h-2.168l4.615 11h13.239l3.474-12h1.929l.743-2h-4.195z'/%3E%3C/svg%3E" alt="">
            </div>

            
        </ul>
    </nav>
</header>

<style>

    header
    {
        width: 100%;
        height: 70px;
    }
    nav
    {
        widows: 100%;
        height: 100%;
    }
    ul
    {
        width: 100%;
        height: 100%;
        display: grid;
        grid-template-columns: 0.2fr  1fr 0.3fr;
        font-weight: 500;
    }
    .logoandcategory
    {
        width:100%;
        height:100%;
        display: grid;
        grid-template-columns: 1fr 1fr;
        justify-content: center;
        align-items:center;
        padding-right: 2px;
        gap: 50px;
        font-weight: 600;
        color:var(--text-primary);
    }
    .signin
    {
        padding: 13px 35px 13px 35px;
        background: var(--amazon-yellow);
        color:white;
        cursor: pointer;
        white-space: nowrap;
    }
    .options
    {
        width: 100%;
        height: 100%;
        justify-content: flex-end;
        align-items: center;
        display: none;
        gap:20px;
        margin-right: 28%;
    }
    
    .category
    {
        display: grid;
        grid-template-columns: 1fr 1.3fr;
        justify-content: center;
        align-items: center;
        gap:10px;
    }
    .logo
    {
        width:100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 2px;
        margin-left: 20px;
    }

    .search
    {
        widows: 100%;
        height:90%;
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 5px;
    }
    .return_cart_icon
    {
        width:100%;
        display: flex;
        gap:60px;
        align-items: center;
        font-weight: 500;
        color:var(--text-primary);
        padding-right: 20px;
    }
 
    .items
    {
        display: flex;
        align-items: center;
        width:80%;
        height:80%;
        border: 2px solid var(--amazon-yellow);
        border-radius: 20px;
        padding-left: 20px;
  
    }
    
    .items img
    {
        margin-right: 20px;
    }
    .search input
    {
        width: 100%;
        border-radius: 50px;
        height: 100%;
        outline: none;
        border: none;
    }

    @media only screen and (max-width:800px)
    {
        ul
        {
            grid-template-columns: none;
            grid-template-rows: 0.2fr  1fr;
            row-gap: 0;
        }
        header
        {
            height: 120px;
        }
        .return_cart_icon
        {
            display:none;
        }
        .options
        {
            display:flex;
        }

        .category
        {
            display: none;
        }
        .logoandcategory
        {
            display: grid;
            grid-template-columns: 0.8fr 1fr;
            justify-items: center;
            gap:0;
            height:60px;
        }
        .logo
        {
            margin-left: 43%;
            justify-content: flex-start;
        }
        .search
        {
            margin: 0;
            background: #232F3E;
        }
        .items
        {
            width: 87%;
        }
        input
        {
            background: transparent;
        }
        ::placeholder 
        {
            color: white;
        }
    }
</style>