<script>
import Category from "./Category.svelte";
import MainNav from "./MainNav.svelte";
import SubNav from "./SubNav.svelte";

const navItems = ['Your Amazon','Your Friends','Todays Deals','Gift Cards','Sell','Help']

let show_categories = false;

</script>
<MainNav on:category_toggle={()=>{show_categories = !show_categories}} />
<Category {show_categories} />
<SubNav {navItems} />
