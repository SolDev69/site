<!-- Code that applies to every single page -->
<!-- <slot /> is a placeholder, it gets replaced by the html of the page currently being viewed -->

<script>
    import "@material/web/iconbutton/outlined-icon-button";
    import "@material/web/icon/icon";

    let navShown = false;
</script>

<header>
    <nav>
        <a class="brand" href="/cursedcreations/">Cursed Creations</a>
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <!-- svelte-ignore a11y-no-static-element-interactions -->
        <md-outlined-icon-button aria-label="Toggle navigation" on:click={() => (navShown = !navShown)}>
            <!-- https://fonts.google.com/icons -->
            <md-icon
                ><svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 -960 960 960" width="24"><path d="M120-240v-80h720v80H120Zm0-200v-80h720v80H120Zm0-200v-80h720v80H120Z" /></svg
                ></md-icon
            >
        </md-outlined-icon-button>
        <ul class="links" class:shown={navShown}>
            {#each [["/", "Home"], ["/cursedcreations/downloads", "Mods"], ["/cursedcreations/wiki", "Wiki"]] as [href, display]}
                <li><a {href}>{display}</a></li>
            {/each}
        </ul>
    </nav>
</header>
<main><slot /></main>