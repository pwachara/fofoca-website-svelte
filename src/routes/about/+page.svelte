<div class="flex flex-wrap">
  <div class="border-r border-gray-200 dark:border-gray-700">
    <nav class="flex flex-col space-y-2" aria-label="Tabs">
      <button class="py-1 pr-4 inline-flex items-center gap-2 border-r-[3px] border-transparent text-sm whitespace-nowrap text-gray-500 hover:text-blue-600 active">
        Tab 1
      </button>
      <button type="button" class="py-1 pr-4 inline-flex items-center gap-2 border-r-[3px] border-transparent text-sm whitespace-nowrap text-gray-500 hover:text-blue-600 dark:hover:text-gray-300">
        Tab 2
      </button>
      <button type="button" class="py-1 pr-4 inline-flex items-center gap-2 border-r-[3px] border-transparent text-sm whitespace-nowrap text-gray-500 hover:text-blue-600 dark:hover:text-gray-300">
        Tab 3
      </button>
    </nav>
  </div>

  <div class="ml-3">
    <div id="vertical-tab-with-border-1" role="tabpanel" aria-labelledby="vertical-tab-with-border-item-1">
      <p class="text-gray-500 dark:text-gray-400">
        This is the <em class="font-semibold text-gray-800 dark:text-gray-200">first</em> item's tab body.
      </p>
    </div>
    <div id="vertical-tab-with-border-2" class="hidden" role="tabpanel" aria-labelledby="vertical-tab-with-border-item-2">
      <p class="text-gray-500 dark:text-gray-400">
        This is the <em class="font-semibold text-gray-800 dark:text-gray-200">second</em> item's tab body.
      </p>
    </div>
    <div id="vertical-tab-with-border-3" class="hidden" role="tabpanel" aria-labelledby="vertical-tab-with-border-item-3">
      <p class="text-gray-500 dark:text-gray-400">
        This is the <em class="font-semibold text-gray-800 dark:text-gray-200">third</em> item's tab body.
      </p>
    </div>
  </div>
</div>

<section id="about" class="bg-[#060a09] min-h-screen">
    
    <div class="container mx-auto py-16 px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 md:grid-cols-2 items-center gap-8">
            <div class="max-w-lg">
                <h2 class="text-3xl font-extrabold text-gray-500 sm:text-4xl">About Us</h2>
                <p class="mt-4 text-gray-600 text-lg">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed quis
                    eros at lacus feugiat hendrerit sed ut tortor. Suspendisse et magna quis elit efficitur consequat.
                    Mauris eleifend velit a pretium iaculis. Donec sagittis velit et magna euismod, vel aliquet nulla
                    malesuada. Nunc pharetra massa lectus, a fermentum arcu volutpat vel.</p>
                <div class="mt-8">
                    <!-- <a href="#" class="text-blue-500 hover:text-blue-600 font-medium">Learn more about us
                        <span class="ml-2">&#8594;</span></a> -->
                </div>
            </div>
            <div class="mt-12 md:mt-0">
                <!-- svelte-ignore a11y-img-redundant-alt -->
                <!-- <img src="/dashboard.svg" alt="About Us Image" class="object-cover rounded-lg shadow-md" /> -->
            </div>
        </div>
    </div>
</section>

<section id="clients" class="flex items-center justify-center min-h-screen">
            <div class="py-14">
            <div class="max-w-screen-xl mx-auto px-4 lg:px-8">
                <h3 class="font-semibold text-sm text-gray-500 text-center">
                    TRUSTED BY TEAMS FROM AROUND THE WORLD
                </h3>
                <div class="mt-6">
                    <ul class="flex gap-y-6 flex-wrap items-center justify-center [&>*]:px-12 lg:divide-x">
                        <li class="flex-none">
                            <img src="https://uploads-ssl.webflow.com/623a29a434fe9111ecdccb63/623a2d6bd1008ebeeabbee14_Group%2029.png" 
                                class="w-48 h-24" 
                                alt="Africa AI logo" />
                        </li>
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
<section id="one" class="flex items-center justify-center min-h-screen bg-white">
            <div class="py-14">
            <div class="max-w-screen-xl mx-auto px-4 lg:px-8">
                <h3 class="font-semibold text-sm text-gray-500 text-center">
                    ONE ONLY!
                </h3>
            </div>
        </div>
</section>