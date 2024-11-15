<script>
    import Header from "./components/header.svelte";
    import Footer from "./components/footer.svelte";

    import Transition from "./components/transition.svelte"

    import "open-props/style"
    import "open-props/normalize"
    import "open-props/buttons"

    import "../app.css"

    export let data
</script>

<div class="layout">
    <Header />

    <main>
        <Transition url={data.url}>
        <slot />
        </Transition>
    </main>

    <Footer />
</div>

<style>
    .layout {
        height: 100%;
        max-inline-size: 1440px;
        display: grid;
        grid-template-rows: auto 1fr auto;
        margin-inline: auto;
        padding-inline: var(--size-7)
    }

    main {
        padding: var(--size-9);
    }

    @media (min-width: 1440px){
        .layout{
            padding-inline: 0;
        }
    }
</style>