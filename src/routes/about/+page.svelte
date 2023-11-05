<aside id="about" class="flex flex-wrap min-h-screen">
  <div class="border-r border-gray-200 grid grid-cols-2 gap-5">
    <nav class="flex flex-col space-y-2" aria-label="Tabs">
      <button class="py-1 pr-4 inline-flex items-center gap-2 border-r-[3px] border-transparent text-sm whitespace-nowrap text-gray-500 hover:text-blue-600 active">
        Tab 1
      </button>
      <button type="button" class="py-1 pr-4 inline-flex items-center gap-2 border-r-[3px] border-transparent text-sm whitespace-nowrap text-gray-500 hover:text-blue-600">
        Tab 2
      </button>
      <button type="button" class="py-1 pr-4 inline-flex items-center gap-2 border-r-[3px] border-transparent text-sm whitespace-nowrap text-gray-500 hover:text-blue-600">
        Tab 3
      </button>
    </nav>
    <div>
      <slot>
        <h1 class="text-5xl text-white">Slot components go here...</h1>
      </slot>
    </div>
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
</aside>

<section id="about2" class="bg-[#060a09] min-h-screen">
    
    <div class="container mx-auto py-16 px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 md:grid-cols-2 items-center gap-8">
            <div class="max-w-lg">
                <h2 class="text-3xl font-extrabold text-gray-500 sm:text-4xl">About Us</h2>
                <p class="mt-4 text-gray-600 text-lg">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed quis
                    eros at lacus feugiat hendrerit sed ut tortor. Suspendisse et magna quis elit efficitur consequat.
                    Mauris eleifend velit a pretium iaculis. Donec sagittis velit et magna euismod, vel aliquet nulla
                    malesuada. Nunc pharetra massa lectus, a fermentum arcu volutpat vel.</p>
                <div class="mt-8">
                </div>
            </div>
            <div class="mt-12 md:mt-0">
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