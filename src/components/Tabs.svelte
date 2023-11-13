<script>
// @ts-nocheck


    import { createEventDispatcher } from "svelte";

    /**
	 * @type {any}
	 */
     export let items;
    /**
	 * @type {any}
	 */
     export let activeItem = false

     let dispatch = createEventDispatcher();

</script>

<div class="tabs min-h-screen">
    <ul class="flex flex-row lg:flex-col lg:gap-5 lg:space-y-3 mx-auto text-gray-400">
        {#each items as item}
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
            <li on:click={() => dispatch("tabChange", item)} class="hover:text-[#fbbf24]">
                <div class:active={ item === activeItem }>
                    { item }
                </div>
            </li>
        {/each}
    </ul>
</div>

<style>
    .tabs {
        margin-bottom: 40px;
    }
    ul {
        display: flex;
        justify-content: center;
        padding: 0;
        list-style: none;
    }
    li {
        margin: 0 16px;
        font-size: 18px;
        /* color: #555555; */
        cursor: pointer;
    }
    .active {
        color: #fbbf24;
        border-bottom: 4px solid #fbbf24;
        padding-bottom: 8px;
    }

    @media (min-width: 640px) {
        .active {
        border-right-width: 4px;
        border-right: 4px solid #fbbf24;
        border-bottom: none;
        }

        li{
            width: 80px;
        }

        ul {
            margin-top: 100px;
        }
    }

</style>