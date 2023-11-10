<script type="ts">
    import { TabGroup, Tab, TabAnchor } from '@skeletonlabs/skeleton';

    let tabSet = 0;
</script>

<TabGroup active="border-b-4 border-r-0 lg:border-r-4 lg:border-b-0 border-[#fbbf24]">

    <div class="flex flex-row lg:flex-col lg:gap-5 lg:absolute lg:left-0 lg:top-28 z-0 border-none lg:min-h-screen lg:w-60 dark:bg-gray-900 dark:text-gray-100">
        <div class="lg:space-y-2">
			<div class="flex flex-row lg:flex-col lg:space-y-3 mx-auto">
                <Tab bind:group={tabSet} name="tab0" value={0}>About Us</Tab>
                <Tab bind:group={tabSet} name="tab1" value={1}>Vision</Tab>
                <Tab bind:group={tabSet} name="tab2" value={2}>Values</Tab>
                <Tab bind:group={tabSet} name="tab3" value={3}>Clients</Tab>
			</div>
		</div>
    </div>


	<!-- Tab Panels --->
	<svelte:fragment slot="panel">
        <div class="text-gray-400 min-h-screen">
            {#if tabSet === 0}
                <section id="about-us" class="flex mx-auto p-10 lg:mx-[15%] min-h-screen">
                    <div class="flex flex-col overflow-hidden rounded-md shadow-sm lg:flex-row">
                        <img src="/at-work-touching-helmet.jpg" alt="" class="h-3/4 dark:bg-gray-500 aspect-auto" loading="lazy">
                        <div class="flex flex-col justify-center flex-1 p-4 dark:bg-gray-900 -mt-24">
                            <h3 class="flex text-3xl font-bold mt-4 lg:mt-0 mx-auto">Our history</h3>
                            <div class="my-6 lg:p-12 dark:text-gray-400 text-xl">
                                <p class="p-6 flex flex-row">
                                    <span class="p-2 text-[#fbbf24]">
                                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
                                            <path fill-rule="evenodd" d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.007 5.404.433c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.433 2.082-5.006z" clip-rule="evenodd" />
                                        </svg>
                                    </span>
                                    <span>
                                        Loka Advisory Services Limited is a HR Advisory and Consultancy services company that was formed in Kenya to ease the burden and step in, when no HR expertise exists to handle your continually needed HR functions.  
                                    </span>
                                </p>
                                <p class="p-6 flex flex-row">
                                    <span class="p-2 text-[#fbbf24]">
                                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
                                            <path fill-rule="evenodd" d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.007 5.404.433c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.433 2.082-5.006z" clip-rule="evenodd" />
                                        </svg>
                                    </span>
                                    <span>
                                        Our functions are typically split between a variety of people, who do not have the training and experience that a HR Consultant brings to the table.
                                    </span>
                                </p>
                                <p class="p-6 flex flex-row">
                                    <span class="p-2 text-[#fbbf24]">
                                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
                                            <path fill-rule="evenodd" d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.007 5.404.433c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.433 2.082-5.006z" clip-rule="evenodd" />
                                        </svg>
                                    </span>
                                    <span>
                                        Loka Advisory lessens the burden for the employer by helping them maximize efficiency of employees leading to higher productivity levels.  Your business will benefit from the expertise and experience of Human Resource Consultants without the cost of paying a full-time salary.
                                    </span>
                                </p>
                            </div>
                        </div>
                    </div>
                </section>
		    {:else if tabSet === 1}
                <section id="vision" class="relative top-0 lg:left-[13%] min-h-screen min-w-full">
                    <img src="/lens.jpg" alt="lens" class="min-h-full w-full object-right-bottom"/>
                        <div class="absolute top-0 lg:top-[12%] lg:left-[12%] flex flex-col bg-transparent">
                            <div class="flex flex-col justify-center p-4 lg:mt-0">
                                <h3 class="flex text-3xl lg:text-6xl font-bold mx-[25%] text-[#fbbf24]">Our Vision</h3>
                                <div class="lg:p-12 dark:text-gray-400 text-xl">
                                    <p class="p-6 flex lg:text-3xl">
                                        To be the most impactful, innovative and efficient HR Consulting partner.
                                    </p>
                                </div>
                            </div>
                            <div class="flex flex-col justify-center flex-1 p-4">
                                    <h3 class="flex text-3xl lg:text-6xl font-bold mx-[25%] text-[#fbbf24]">Our Mission</h3>
                                    <div class="my-6 lg:p-12 dark:text-gray-400 text-xl">
                                        <p class="p-6 flex lg:text-3xl flex-wrap lg:leading-10 lg:max-w-[75%]">
                                            We are a professional, enthusiastic and innovative team, 
                                            dedicated to providing professional HR consulting services and 
                                            evolving recruitment solutions that help our customers become more productive and profitable.
                                        </p>
                                    </div>
                            </div>
                        </div>
                </section>
            {:else if tabSet === 2}
                <section id="values" class="object-cover lg:h-1/2 lg:w-1/2 mx-auto">
                    <img src="/values.jpg" alt="values" loading="lazy"/>
                </section>
            
            {:else if tabSet === 3}
                <section id="clients" class="flex mx-auto min-h-screen">
                        <div class="max-w-screen-xl mx-auto">
                            <h3 class="font-semibold text-sm text-gray-500 text-center mb-10">
                                TRUSTED BY TEAMS FROM AROUND THE WORLD
                            </h3>
                            <div class="flex flex-col lg:flex-row">
                                <ul class="flex flex-col lg:flex-row gap-y-6 items-center justify-center">
                                    <li>
                                        <img src="/africa-ai.png" 
                                            class="w-48 h-24" 
                                            alt="Africa AI logo" loading="lazy" />
                                    </li>
                                    <li><span class="lg:pr-12 lg:border-r-4 border-slate-500 lg:mr-12 text-5xl"></span></li>
                                    <li>
                                        <img src="/apni.png"
                                            class="w-48 h-12"
                                            alt="Africa Plant Nutrition logo" loading="lazy" />
                                    </li>
                                </ul>
                            </div>
                        </div>
                </section>
            {/if}
        </div>
	</svelte:fragment>
</TabGroup>
			






				