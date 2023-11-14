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

<div class="flex flex-col md:flex-row">
    <Tabs {items} {activeItem} on:tabChange={ tabChange }/>
    {#if activeItem === "About"}
        <div class="min-w-full mt-4">
            <About />
        </div>
    {:else if activeItem === "Vision"}
        <div class="min-w-full mt-4">
            <Vision />
        </div>
    {:else if activeItem === "Values"}
        <div class="min-w-full mt-4">
            <Values />
        </div>
    {:else if activeItem === "Clients"}
        <div class="min-w-full mt-4 md:p-40">
            <Clients />
        </div>
    {/if}
</div>

<style>

</style>

