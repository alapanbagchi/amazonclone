<script>


import Navbar from "../components/Navbar.svelte";
import FeedUserTemplate from "../components/FeedUserTemplate.svelte";
import Slider from "../components/Slider.svelte";
import UserData from "../components/UserData.svelte";
import Footer from "../components/Footer.svelte";

const TemplateData = [


    {
        navItems:['Featured','Fashion','Children','Audio'],
        posterImage:'https://images.unsplash.com/photo-1515110371136-7e393289662c?ixlib=rb-1.2.1&ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&auto=format&fit=crop&w=756&q=80 756w',
        posterTitle:'Based on items you\'ve recently seen',
        posterSlogan:'Based on your history, we have gathered all the best offers for you',
        products:[
            {
                name:'Kids Polo',
                companyName:'Lacoste',
                image:'./assets/products/tshirt.png',
                price:'$45',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'Staple 100',
                companyName:'BOSS',
                image:'./assets/products/black-shoe-heels.png',
                price:'$285',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'Staple 100',
                companyName:'BOSS',
                image:'./assets/products/black-shoe-heels.png',
                price:'$285',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'Staple 100',
                companyName:'BOSS',
                image:'./assets/products/black-shoe-heels.png',
                price:'$285',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'Staple 100',
                companyName:'BOSS',
                image:'./assets/products/black-shoe-heels.png',
                price:'$285',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'H8 Headphone',
                companyName:'Beoplay',
                image:'./assets/products/headphone.png',
                price:'$399',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'Yatch Master Rubber',
                companyName:'Rolex',
                image:'./assets/products/watch.png',
                price:'$8,995',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'H8 Headphone',
                companyName:'Beoplay',
                image:'./assets/products/headphone.png',
                price:'$399',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'H8 Headphone',
                companyName:'Beoplay',
                image:'./assets/products/headphone.png',
                price:'$399',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'H8 Headphone',
                companyName:'Beoplay',
                image:'./assets/products/headphone.png',
                price:'$399',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'H8 Headphone',
                companyName:'Beoplay',
                image:'./assets/products/headphone.png',
                price:'$399',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'H8 Headphone',
                companyName:'Beoplay',
                image:'./assets/products/headphone.png',
                price:'$399',
                color:['#000000','#fccda2'],
                section:'Featured'
            },

        ]

    },
    {
        navItems:['Featured','Fashion','Children','Audio'],
        posterImage:'https://images.unsplash.com/photo-1515110371136-7e393289662c?ixlib=rb-1.2.1&ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&auto=format&fit=crop&w=756&q=80 756w',
        posterTitle:'Based on items you\'ve recently seen',
        posterSlogan:'Based on your history, we have gathered all the best offers for you',
        products:[
            {
                name:'Kids Polo',
                companyName:'Lacoste',
                image:'./assets/products/tshirt.png',
                price:'$45',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'Staple 100',
                companyName:'BOSS',
                image:'./assets/products/black-shoe-heels.png',
                price:'$285',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'Staple 100',
                companyName:'BOSS',
                image:'./assets/products/black-shoe-heels.png',
                price:'$285',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'Staple 100',
                companyName:'BOSS',
                image:'./assets/products/black-shoe-heels.png',
                price:'$285',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'Staple 100',
                companyName:'BOSS',
                image:'./assets/products/black-shoe-heels.png',
                price:'$285',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'H8 Headphone',
                companyName:'Beoplay',
                image:'./assets/products/headphone.png',
                price:'$399',
                color:['#000000','#fccda2'],
                section:'Featured'
            },
            {
                name:'Yatch Master Rubber',
                companyName:'Rolex',
                image:'./assets/products/watch.png',
                price:'$8,995',
                color:['#000000','#fccda2'],
                section:'Fashion'
            },
            {
                name:'H8 Headphone',
                companyName:'Beoplay',
                image:'./assets/products/headphone.png',
                price:'$399',
                color:['#000000','#fccda2'],
                section:'Fashion'
            },
            {
                name:'H8 Headphone',
                companyName:'Beoplay',
                image:'./assets/products/headphone.png',
                price:'$399',
                color:['#000000','#fccda2'],
                section:'Fashion'
            },
            {
                name:'H8 Headphone',
                companyName:'Beoplay',
                image:'./assets/products/headphone.png',
                price:'$399',
                color:['#000000','#fccda2'],
                section:'Fashion'
            },
            {
                name:'H8 Headphone',
                companyName:'Beoplay',
                image:'./assets/products/headphone.png',
                price:'$399',
                color:['#000000','#fccda2'],
                section:'Fashion'
            },
            {
                name:'H8 Headphone',
                companyName:'Beoplay',
                image:'./assets/products/headphone.png',
                price:'$399',
                color:['#000000','#fccda2'],
                section:'Children'
            },

        ]

    },
    
    


]

const footer = [
    {
        name:'Get to know us',
        content:['Careers','Blog','About Us','Investor Relation','Amazon Devices','Amazon Tours']
    },
    {
        name:'Make money with Us',
        content:['Sell products on Amazon','Sell apps on Amazon','Become a affiliate','Advertise your products','Self Publish with us','Host an Amazon Hub','See More Make Money with us']
    },
    {
        name:'Amazon Payment Products',
        content:['Amazon Buisness Card','Shop with points','Reload your Balance','Amazon Currency Converter']
    },
    {
        name:'Let Us Help You',
        content:['Amazon and COVID-19','Your Account','Your Orders','Shipping Rates & Policies','Returns and Replacements','Manage your Content and Devices','Amazon Assistant','Help']
    },
    {
        name:'Amazon Owned Brands',
        content:['Amazon Music','Prime Videos','Kindle','Souq.com','DPR reviews']
    },
]



</script>
<Navbar />


<UserData />
<!-- <Slider /> -->

{#each TemplateData as data,i}

        <FeedUserTemplate index={i} navItems={data.navItems} posterImage={data.posterImage} posterTitle={data.posterTitle} posterSlogan={data.posterSlogan} products={data.products}/>

{/each}

<!-- <Footer footer = {footer} /> -->
