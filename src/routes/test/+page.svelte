<script>
    import Tabs from "../../components/Tabs.svelte";
    import About from "../../components/About.svelte"
    import Vision from "../../components/Vision.svelte"
    import Values from "../../components/Values.svelte"
    import Clients from "../../components/Clients.svelte"

    let items = ["About", "Vision", "Values", "Clients"];
    let activeItem = "About";

    const tabChange = (e) => {
        activeItem = e.detail;
     }

</script>

<section>
    <Tabs {items} {activeItem} on:tabChange={ tabChange }/>
    {#if activeItem === "About"}
        <About />
    {:else if activeItem === "Vision"}
        <Vision />
    {:else if activeItem === "Values"}
        <Values />
    {:else if activeItem === "Clients"}
        <Clients />
    {/if}
</section>

<style>

</style>

