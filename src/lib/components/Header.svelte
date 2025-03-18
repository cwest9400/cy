<script>
    import { onMount } from "svelte";

    let isScrolled = false;

    onMount(() => {
        const handleScroll = () => {
            isScrolled = window.scrollY > 50; // changes when user scrolls 50px
        };

        window.addEventListener("scroll", handleScroll);
    });
</script>


<header class="{isScrolled ? 'scrolled' : ''}">
    <nav class="nav-container">
      <div class="logo-container">LOGO</div>
      <ul class="link-container">
        <li><a href="/services&products">SERVICES & PRODUCTS</a></li>
        <li><a href="/industries">INDUSTRIES</a></li>
        <li><a href="/about">ABOUT</a></li>
        <li><a href="/contact">CONTACT</a></li>
      </ul>
    </nav>
</header>

<style>
    header {
        position: fixed;
        top: 0;
        left: 0;
        color: white; /* Ensures all text inside the header is white */
        background-color: #162867;
        padding: 10px 20px;
        width: 100vw;
        max-width: 100%;
        transition: background-color 0.3s ease-in-out;
        z-index: 1000;
        box-sizing: border-box;
    }

    header:not(.scrolled) {
        background-color: transparent;
    }

    .scrolled {
        background-color: #162867;
    }
    

    .nav-container {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .logo-container {
        color: white; /* Explicitly set white in case of inheritance issues */
        max-width: 350px;
    }

    .link-container {
        display: flex;
        flex-direction: row;
        list-style: none; /* Removes bullet points */
        padding: 0;
        margin: 0;
    }

    .link-container li {
        margin-left: 20px; /* Adds spacing between nav items */
    }

    .link-container a {
        text-decoration: none; /* Removes underline */
        color: inherit; /* Ensures text color matches the parent */
        font: inherit; /* Uses document font */
    }

    /* Contact Button */
.link-container li:last-child a {
    background-color: #162867;
    color: white;
    padding: 10px 20px;
    border-radius: 4px;
    transition: background-color 0.3s ease-in-out, color 0.3s ease-in-out;
}

/* Contact Button Hover */
.link-container li:last-child a:hover {
    background-color: white;
    color: #162867;
}

/* Change Font Color on Hover for Other Links */
.link-container li:not(:last-child) a:hover {
    color: #162867;
}

</style>
