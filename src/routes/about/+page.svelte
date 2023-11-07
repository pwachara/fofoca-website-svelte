<script type="ts">
    import { TabGroup, Tab, TabAnchor } from '@skeletonlabs/skeleton';

    let tabSet = 0;
</script>

<TabGroup active="border-b-4 border-r-0 lg:border-r-4 lg:border-b-0 border-[#fbbf24]">

    <div class="flex flex-row lg:flex-col lg:gap-5 lg:absolute lg:left-0 lg:top-28 z-0 border-none lg:min-h-screen p-6 lg:w-60 dark:bg-gray-900 dark:text-gray-100">
        <div class="lg:space-y-2">
			<div class="flex flex-row lg:flex-col lg:space-y-3 mx-auto">
                <Tab bind:group={tabSet} name="tab1" value={0}>About Us</Tab>
                <Tab bind:group={tabSet} name="tab2" value={1}>Clients</Tab>
                <Tab bind:group={tabSet} name="tab3" value={2}>Other</Tab>
			</div>
		</div>
    </div>


	<!-- Tab Panels --->
	<svelte:fragment slot="panel">

        <div class="absolute left-1/4 top-1/4 z-0 h-full text-gray-400">

            {#if tabSet === 0}
			<section class="container p-14">
                <p>
                    Loka Advisory Services Limited is a HR Advisory and Consultancy services company that was formed in Kenya to ease the burden and step in, when no HR expertise exists to handle your continually needed HR functions.  Our functions are typically split between a variety of people, who do not have the training and experience that an HR Consultant brings to the table.  Loka Advisory lessens the burden for the employer by helping them maximize efficiency of employees leading to higher productivity levels.  Your business will benefit from the expertise and experience of Human Resource Consultants without the cost of paying a full-time salary.
                </p>
            </section>
		    {:else if tabSet === 1}
                <section id="clients" class="flex items-center justify-center">
                    <div class="py-14">
                        <div class="max-w-screen-xl mx-auto px-4 lg:px-8">
                            <h3 class="font-semibold text-sm text-gray-500 text-center">
                                TRUSTED BY TEAMS FROM AROUND THE WORLD
                            </h3>
                            <div class="mt-6 flex">
                                <ul class="flex gap-y-6 flex-wrap items-center justify-center">
                                    <li class="flex-none">
                                        <img src="https://uploads-ssl.webflow.com/623a29a434fe9111ecdccb63/623a2d6bd1008ebeeabbee14_Group%2029.png" 
                                            class="w-48 h-24" 
                                            alt="Africa AI logo" />
                                    </li>
                                    <li><span class="pr-12 border-r-4 border-slate-500 mr-12 text-5xl"></span></li>
                                    <li class="flex-none">
                                        <img src="https://www.apni.net/wp-content/uploads/2020/07/APNI-header-82.png"
                                            class="w-48 h-12"
                                            alt="Africa Plant Nutrition logo" />
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </section>
            {:else if tabSet === 2}
                <h1 class="text-5xl text-yellow-500">Other contents go here...</h1>
            {/if}

        </div>
	</svelte:fragment>
</TabGroup>
			






				