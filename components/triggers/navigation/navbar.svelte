<script>
    // components
    import NavbarLink from "../buttons/navbar_link.svelte"
</script>

<div class="global-navigation--gradient">
</div>
<nav class="global-navigation--links-wrapper">
    <NavbarLink iconSrc={'assets/images/icons/bell.png'}/>
</nav>

<style>
    .global-navigation--gradient{
        width: 100vw;
        height: 1rem;
        position: fixed;
        top: 0;
        left: 0;
        background-image: linear-gradient(45deg, var(--graient-one), var(--gradient-two), var(--graient-one), var(--gradient-two));
        background-size: 400% 100%;
        animation: NavbarGradient 2000ms ease infinite;
        animation-direction: alternate;
    }

    @keyframes NavbarGradient {
        0% {
            background-position: 0%;
        }
        100% {
            background-position: 100%;
        }
    }
    .global-navigation--links-wrapper{ 
        width: 100vw;
        height: 5rem;
        display: block;
        position: fixed;
        top: 3rem;
        left: 4%;
    }
</style>