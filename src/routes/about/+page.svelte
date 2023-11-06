<script>
    import { TabGroup, Tab, TabAnchor } from '@skeletonlabs/skeleton';
    let tabSet = 0;
</script>


<TabGroup active="border-r-4 border-[#fbbf24]">

    <div class="flex lg:flex-col lg:gap-5 absolute left-0 top-32 border-none min-h-screen p-6 sm:w-60 dark:bg-gray-900 dark:text-gray-100">

        <div class="space-y-2">
			<div class="flex flex-col space-y-3">
                <Tab bind:group={tabSet} name="tab1" value={0}>About Us</Tab>
                <Tab bind:group={tabSet} name="tab2" value={1}>Clients</Tab>
                <Tab bind:group={tabSet} name="tab3" value={2}>Other</Tab>
			</div>
		</div>




    </div>


	<!-- Tab Panels --->
	<svelte:fragment slot="panel">

        <div class="absolute left-1/4 top-1/4">

            {#if tabSet === 0}
			<p class="container p-14">Lorem ipsum dolor sit amet consectetur adipisicing elit. Nesciunt dolorem deleniti blanditiis animi laudantium aspernatur similique cumque libero odit numquam, tempore aperiam maiores voluptatum ea consequuntur quo id incidunt tenetur.
            Quaerat, delectus vero repellendus excepturi nostrum eaque blanditiis soluta id, dolorem debitis assumenda reprehenderit. Quos quia perspiciatis laudantium facilis eligendi illo minima error necessitatibus consequatur tempora, reiciendis odio aliquam eos!
            Nemo, dolores autem perferendis soluta ut aspernatur hic possimus ea eius magni reiciendis officiis voluptas maxime enim culpa asperiores quasi nihil cumque natus. Autem nihil officia corporis illum aspernatur rem.
            Quas, atque quod laborum esse magni sequi dolorum cupiditate nam, labore explicabo vel eum doloribus possimus repellat! Maiores, minima qui! Explicabo facere quidem accusantium nemo dolores ipsa eum veritatis ipsum.
            Id, numquam corporis? Recusandae, voluptatum! Iure in quaerat modi magnam quibusdam eligendi, necessitatibus nostrum. Excepturi assumenda unde dolorem quos ut. Magni reiciendis expedita non explicabo, perferendis sapiente commodi omnis ex.
            Laudantium, quod nesciunt corporis ipsa cumque nulla neque aliquam voluptatibus dolores at magnam tempora qui facilis iure, maxime veritatis debitis esse dolore iste eaque nemo natus. Alias reprehenderit rerum nam.
            Id dolores asperiores dolor amet voluptates, nobis, perspiciatis dignissimos quas, quibusdam illo dolore non exercitationem illum minima nisi! Ratione debitis voluptates aperiam quidem necessitatibus numquam mollitia neque quia laboriosam eligendi.
            Explicabo placeat aperiam repudiandae incidunt, sed accusantium, dicta similique rerum eos, aut repellat. Temporibus, animi. Magni blanditiis animi nisi laudantium fugiat ea alias, nemo maiores distinctio, excepturi enim sint cum.
            Ex sapiente repellendus veniam doloremque veritatis quibusdam similique! Dignissimos quae, at aut natus, laudantium placeat iusto possimus libero corporis assumenda, reiciendis commodi obcaecati ipsam optio culpa. Soluta nam sapiente saepe.
            Quis, sequi neque? Id ab suscipit ut iure necessitatibus et. Rerum totam hic impedit qui consequuntur ullam quaerat, quisquam eaque. Facilis iste optio tenetur perspiciatis unde. Et asperiores eos ducimus!</p>
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
			






				