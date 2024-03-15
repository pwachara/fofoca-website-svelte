<script>
	// @ts-ignore
	import Carousel from 'svelte-carousel'
	import { browser } from '$app/environment'
	import { onMount } from 'svelte';

/** @type {HTMLElement} */
  let nextDom;
  let prevDom;
  let carouselDom;
  let sliderDom;
  let thumbnailBorderDom;
  let thumbnailItemsDom;
  let timeDom;
  //let emptyDiv = document.createElement('span')

  onMount(() => {
    // Get references to DOM elements
    nextDom = document.getElementById('next')
    prevDom = document.getElementById('prev')
    carouselDom = document.querySelector('.carousel')
    sliderDom = carouselDom?.querySelector('.carousel .list')
    thumbnailBorderDom = document.querySelector('.carousel .thumbnail')
    thumbnailItemsDom = thumbnailBorderDom?.querySelectorAll('.item')
    timeDom = document.querySelector('.carousel .time')

    // Append first thumbnail item
    thumbnailBorderDom.appendChild(thumbnailItemsDom[0])

    // Set up click event listeners
    nextDom.onclick = () => showSlider('next')
    prevDom.onclick = () => showSlider('prev')

    // Set up automatic sliding
    let runTimeOut;
    let runNextAuto = setTimeout(() => {
        nextDom.click()

    }, 7000)

    function showSlider(type) {
      let sliderItemsDom = sliderDom.querySelectorAll('.carousel .list .item')
      let thumbnailItemsDom = document.querySelectorAll('.carousel .thumbnail .item')

      if (type === 'next') {
        sliderDom.appendChild(sliderItemsDom[0]);
        thumbnailBorderDom.appendChild(thumbnailItemsDom[0])
        carouselDom.classList.add('next')
      } else {
        sliderDom.prepend(sliderItemsDom[sliderItemsDom.length - 1])
        thumbnailBorderDom.prepend(thumbnailItemsDom[thumbnailItemsDom.length - 1])
        carouselDom.classList.add('prev')
      }

      clearTimeout(runTimeOut);
      	runTimeOut = setTimeout(() => {
        carouselDom.classList.remove('next')
        carouselDom.classList.remove('prev')
      }, 3000);

      clearTimeout(runNextAuto);
      	runNextAuto = setTimeout(() => {
        nextDom.click()
      }, 7000)
    }
  });

	//For the footer date
	let thisYear = new Date().getFullYear().toString()	
</script>

<section id="home" class="relative bg-[url(/dance-floor.jpg)] bg-cover bg-right-top bg-no-repeat object-left-top">
	<div class="bg-black/50 lg:bg-black/10 ">
		<div class=" max-w-screen lg:ml-96 min-h-screen lg:p-32">
			  <div class="max-w-xl text-center">
				  <div class="pt-10 lg:pt-0 text-white lg:text-[#a91012] font-extrabold ">
						<h1 class="text-5xl sm:text-9xl">
							Comida Caseira
						</h1>
					  <p class="text-black text-5xl sm:text-6xl">
						  fora de casa.
					  </p>
				  </div>
				  <!-- <h1 class="pt-10 lg:pt-0 text-5xl text-black font-extrabold sm:text-6xl">
					  Home food
					  <strong class="block font-extrabold text-[#a91012]">
						  away from home.
					  </strong>
				  </h1> -->
	  
				  <p class="px-10 lg:px-0 flex justify-center text-white mt-4 max-w-lg sm:text-xl/relaxed">
					  Desfrute de nossa deliciosa comida com amigos e familiares enquanto acompanha os acontecimentos do dia.
				  </p>
				  <!-- <p class="px-10 lg:px-0 flex justify-center text-white mt-4 max-w-lg sm:text-xl/relaxed">
					  Enjoy our delicious food with friends and family as you catch up with the day's events.
				  </p> -->
	  
				  <div class="mt-8 flex text-center justify-center">
					  <a href="#nothing-here" class="w-full rounded bg-[#a91012] px-12 py-3 text-sm font-medium text-white shadow hover:bg-rose-700 focus:outline-none focus:ring active:bg-rose-500 sm:w-auto">
						  Peça agora
					  </a>
				  </div>
			  </div>
		</div>
	</div>
</section>

<section id="services" class="flex flex-col  bg-gray-800 text-gray-100 min-h-screen pt-10">
	<h3 class="flex text-6xl text-[#a91012] mx-auto">Serviços de catering</h3>
	<div class="flex flex-col p-36 lg:flex-row gap-40 min-h-screen">	
		<article class="overflow-hidden rounded-lg shadow transition hover:shadow-lg">
			<img
				alt="Office"
				src="https://images.unsplash.com/photo-1524758631624-e2822e304c36?ixlib=rb-1.2.1&ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2070&q=80"
				class="h-56 w-full object-cover"
			/>
	
			<div class="bg-white p-4 sm:p-6">
				<div class="flex text-xs text-[#a91012]">
					<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-16 h-16">
  						<path d="M15 1.784l-.796.796a1.125 1.125 0 101.591 0L15 1.784zM12 1.784l-.796.796a1.125 1.125 0 101.591 0L12 1.784zM9 1.784l-.796.796a1.125 1.125 0 101.591 0L9 1.784zM9.75 7.547c.498-.02.998-.035 1.5-.042V6.75a.75.75 0 011.5 0v.755c.502.007 1.002.021 1.5.042V6.75a.75.75 0 011.5 0v.88l.307.022c1.55.117 2.693 1.427 2.693 2.946v1.018a62.182 62.182 0 00-13.5 0v-1.018c0-1.519 1.143-2.829 2.693-2.946l.307-.022v-.88a.75.75 0 011.5 0v.797zM12 12.75c-2.472 0-4.9.184-7.274.54-1.454.217-2.476 1.482-2.476 2.916v.384a4.104 4.104 0 012.585.364 2.605 2.605 0 002.33 0 4.104 4.104 0 013.67 0 2.605 2.605 0 002.33 0 4.104 4.104 0 013.67 0 2.605 2.605 0 002.33 0 4.104 4.104 0 012.585-.364v-.384c0-1.434-1.022-2.7-2.476-2.917A49.138 49.138 0 0012 12.75zM21.75 18.131a2.604 2.604 0 00-1.915.165 4.104 4.104 0 01-3.67 0 2.604 2.604 0 00-2.33 0 4.104 4.104 0 01-3.67 0 2.604 2.604 0 00-2.33 0 4.104 4.104 0 01-3.67 0 2.604 2.604 0 00-1.915-.165v2.494c0 1.036.84 1.875 1.875 1.875h15.75c1.035 0 1.875-.84 1.875-1.875v-2.494z" />
					</svg>
				</div>
					<h3 class="mt-0.5 text-lg text-gray-900 font-semibold">
						Birthday Parties
					</h3>
				<p class="mt-2 line-clamp-3 text-sm/relaxed text-gray-500">
				Lorem ipsum dolor sit amet, consectetur adipisicing elit. Recusandae
				dolores, possimus pariatur animi temporibus nesciunt praesentium dolore
				sed nulla ipsum eveniet corporis quidem, mollitia itaque minus soluta,
				voluptates neque explicabo tempora nisi culpa eius atque dignissimos.
				Molestias explicabo corporis voluptatem?
				</p>
			  </div>
		</article>
		<article class="overflow-hidden rounded-lg shadow transition hover:shadow-lg">
			<img
				alt="Office"
				src="https://images.unsplash.com/photo-1524758631624-e2822e304c36?ixlib=rb-1.2.1&ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2070&q=80"
				class="h-56 w-full object-cover"
			/>
	
			<div class="bg-white p-4 sm:p-6">
				<div class="block text-xs text-[#a91012]">
					<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-16 h-16">
  						<path d="M11.7 2.805a.75.75 0 01.6 0A60.65 60.65 0 0122.83 8.72a.75.75 0 01-.231 1.337 49.949 49.949 0 00-9.902 3.912l-.003.002-.34.18a.75.75 0 01-.707 0A50.009 50.009 0 007.5 12.174v-.224c0-.131.067-.248.172-.311a54.614 54.614 0 014.653-2.52.75.75 0 00-.65-1.352 56.129 56.129 0 00-4.78 2.589 1.858 1.858 0 00-.859 1.228 49.803 49.803 0 00-4.634-1.527.75.75 0 01-.231-1.337A60.653 60.653 0 0111.7 2.805z" />
  						<path d="M13.06 15.473a48.45 48.45 0 017.666-3.282c.134 1.414.22 2.843.255 4.285a.75.75 0 01-.46.71 47.878 47.878 0 00-8.105 4.342.75.75 0 01-.832 0 47.877 47.877 0 00-8.104-4.342.75.75 0 01-.461-.71c.035-1.442.121-2.87.255-4.286A48.4 48.4 0 016 13.18v1.27a1.5 1.5 0 00-.14 2.508c-.09.38-.222.753-.397 1.11.452.213.901.434 1.346.661a6.729 6.729 0 00.551-1.608 1.5 1.5 0 00.14-2.67v-.645a48.549 48.549 0 013.44 1.668 2.25 2.25 0 002.12 0z" />
  						<path d="M4.462 19.462c.42-.419.753-.89 1-1.394.453.213.902.434 1.347.661a6.743 6.743 0 01-1.286 1.794.75.75 0 11-1.06-1.06z" />
					</svg>
				</div>
				<h3 class="mt-0.5 text-lg text-gray-900 font-semibold">
					Graduation Parties
				</h3>
				<p class="mt-2 line-clamp-3 text-sm/relaxed text-gray-500">
				Lorem ipsum dolor sit amet, consectetur adipisicing elit. Recusandae
				dolores, possimus pariatur animi temporibus nesciunt praesentium dolore
				sed nulla ipsum eveniet corporis quidem, mollitia itaque minus soluta,
				voluptates neque explicabo tempora nisi culpa eius atque dignissimos.
				Molestias explicabo corporis voluptatem?
				</p>
			  </div>
		</article>
		<article class="overflow-hidden rounded-lg shadow transition hover:shadow-lg">
			<img
				alt="Office"
				src="https://images.unsplash.com/photo-1524758631624-e2822e304c36?ixlib=rb-1.2.1&ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2070&q=80"
				class="h-56 w-full object-cover"
			/>
	
			<div class="bg-white p-4 sm:p-6">
				<div class="block text-xs text-[#a91012]">
					<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-16 h-16">
  						<path d="M9.375 3a1.875 1.875 0 000 3.75h1.875v4.5H3.375A1.875 1.875 0 011.5 9.375v-.75c0-1.036.84-1.875 1.875-1.875h3.193A3.375 3.375 0 0112 2.753a3.375 3.375 0 015.432 3.997h3.943c1.035 0 1.875.84 1.875 1.875v.75c0 1.036-.84 1.875-1.875 1.875H12.75v-4.5h1.875a1.875 1.875 0 10-1.875-1.875V6.75h-1.5V4.875C11.25 3.839 10.41 3 9.375 3zM11.25 12.75H3v6.75a2.25 2.25 0 002.25 2.25h6v-9zM12.75 12.75v9h6.75a2.25 2.25 0 002.25-2.25v-6.75h-9z" />
					</svg>
				</div>
				<h3 class="mt-0.5 text-lg text-gray-900 font-semibold">
					Office Parties
				</h3>

	
				<p class="mt-2 line-clamp-3 text-sm/relaxed text-gray-500">
				Lorem ipsum dolor sit amet, consectetur adipisicing elit. Recusandae
				dolores, possimus pariatur animi temporibus nesciunt praesentium dolore
				sed nulla ipsum eveniet corporis quidem, mollitia itaque minus soluta,
				voluptates neque explicabo tempora nisi culpa eius atque dignissimos.
				Molestias explicabo corporis voluptatem?
				</p>
			  </div>
		</article>
	</div>
</section>

<section id="engagements" class=" min-h-screen flex mx-auto lg:pr-48">

	<h1 class="h1">Engagements section</h1>
  
</section>

<section id="menu" class=" min-h-screen flex mx-auto lg:px-24">
	<!-- carousel -->
    <div class="carousel">
        <!-- list item -->
        <div class="list">
            <div class="item">
                <img src="./img1.jpg" alt="1">
                <div class="content">
                    <div class="author">LUNDEV</div>
                    <div class="title">DESIGN SLIDER</div>
                    <div class="topic">ANIMAL</div>
                    <div class="des">
                        <!-- lorem 50 -->
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ut sequi, rem magnam nesciunt minima placeat, itaque eum neque officiis unde, eaque optio ratione aliquid assumenda facere ab et quasi ducimus aut doloribus non numquam. Explicabo, laboriosam nisi reprehenderit tempora at laborum natus unde. Ut, exercitationem eum aperiam illo illum laudantium?
                    </div>
                    <div class="buttons">
                        <button>SEE MORE</button>
                        <button>SUBSCRIBE</button>
                    </div>
                </div>
            </div>
            <div class="item">
                <img src="./img2.jpg" alt="2">
                <div class="content">
                    <div class="author">LUNDEV</div>
                    <div class="title">DESIGN SLIDER</div>
                    <div class="topic">ANIMAL</div>
                    <div class="des">
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ut sequi, rem magnam nesciunt minima placeat, itaque eum neque officiis unde, eaque optio ratione aliquid assumenda facere ab et quasi ducimus aut doloribus non numquam. Explicabo, laboriosam nisi reprehenderit tempora at laborum natus unde. Ut, exercitationem eum aperiam illo illum laudantium?
                    </div>
                    <div class="buttons">
                        <button>SEE MORE</button>
                        <button>SUBSCRIBE</button>
                    </div>
                </div>
            </div>
            <div class="item">
                <img src="./img3.jpg" alt="3">
                <div class="content">
                    <div class="author">LUNDEV</div>
                    <div class="title">DESIGN SLIDER</div>
                    <div class="topic">ANIMAL</div>
                    <div class="des">
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ut sequi, rem magnam nesciunt minima placeat, itaque eum neque officiis unde, eaque optio ratione aliquid assumenda facere ab et quasi ducimus aut doloribus non numquam. Explicabo, laboriosam nisi reprehenderit tempora at laborum natus unde. Ut, exercitationem eum aperiam illo illum laudantium?
                    </div>
                    <div class="buttons">
                        <button>SEE MORE</button>
                        <button>SUBSCRIBE</button>
                    </div>
                </div>
            </div>
            <div class="item">
                <img src="/img4.jpg" alt="4">
                <div class="content">
                    <div class="author">LUNDEV</div>
                    <div class="title">DESIGN SLIDER</div>
                    <div class="topic">ANIMAL</div>
                    <div class="des">
                        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ut sequi, rem magnam nesciunt minima placeat, itaque eum neque officiis unde, eaque optio ratione aliquid assumenda facere ab et quasi ducimus aut doloribus non numquam. Explicabo, laboriosam nisi reprehenderit tempora at laborum natus unde. Ut, exercitationem eum aperiam illo illum laudantium?
                    </div>
                    <div class="buttons">
                        <button>SEE MORE</button>
                        <button>SUBSCRIBE</button>
                    </div>
                </div>
            </div>
        </div>
        <!-- list thumnail -->
        <div class="thumbnail">
            <div class="item">
                <img src="./img1.jpg" alt="1">
                <!-- <div class="content">
                    <div class="title">
                        Name Slider
                    </div>
                    <div class="description">
                        Description
                    </div>
                </div> -->
            </div>
            <div class="item">
                <img src="./img2.jpg" alt="2">
                <!-- <div class="content">
                    <div class="title">
                        Name Slider
                    </div>
                    <div class="description">
                        Description
                    </div>
                </div> -->
            </div>
            <div class="item">
                <img src="./img3.jpg" alt="3">
                <!-- <div class="content">
                    <div class="title">
                        Name Slider
                    </div>
                    <div class="description">
                        Description
                    </div>
                </div> -->
            </div>
            <div class="item">
                <img src="./img4.jpg" alt="4">
                <div class="content">
                    <!-- <div class="title">
                        Name Slider
                    </div> -->
                    <!-- <div class="description">
                        Description
                    </div> -->
                </div>
            </div>
        </div>

        <!-- next prev -->

        <div class="arrows">
            <!-- <button id="prev">Prev</button>
            <button id="next">Next</button> -->
            <button class="button" id="prev">Prev</button>
            <button class="button" id="next">Next</button>
        </div>
        <!-- time running -->
        <div class="time"></div>
    </div>
</section>

<section id="faqs" class="bg-gray-800 text-gray-300 min-h-screen">
	<div class="container flex flex-col flex-wrap justify-center p-4 mx-auto lg:p-8">
		<h2 class="mb-12 text-4xl font-bold leading-10 text-center lg:text-5xl">Frequently asked questions</h2>
		<div class="flex flex-col lg:px-32 gap-y-3">
			<details>
				<summary class="ring-1 ring-amber-400 opacity-70 p-4 cursor-pointer mb-4 text-gray-300 font-bold rounded-lg hover:opacity-90">We are looking to set up operations in Kenya for the first time. Can you be of help?</summary>
				<div class="px-6 pb-6">
					<p>Yes, we can help establish a HR infrastructure that will not only effectively support your business needs from the onset, but also comply with all the local labour laws.</p>
				</div>
			</details>
			<details>
				<summary class="ring-1 ring-amber-400 opacity-70 p-4 outline-none cursor-pointer mb-4 text-gray-300 font-bold rounded-lg">Can you help me determine whether I am paying my staff adequately?</summary>
				<div class="px-6 pb-6">
					<p>Yes, we will perform salary benchmarking exercises to ensure competitiveness in your industry.  Salaries, Pension Schemes, Medical Covers, Group Life Insurance etc. will be reviewed and the necessary advice given.</p>
				</div>
			</details>
			<details>
				<summary class="ring-1 ring-amber-400 opacity-70 p-4 outline-none cursor-pointer mb-4 text-gray-300 font-bold rounded-lg">We are lagging behind in our CBA negotiations. Can you help?</summary>
				<div class="px-6 pb-6 space-y-2">
					<p>Yes, we can help you negotiate all your collective bargaining agreements (CBAs) and foster cordial relations with the union shop stewards and union officials.</p>
				</div>
			</details>
			<details>
				<summary class="ring-1 ring-amber-400 opacity-70 p-4 outline-none cursor-pointer mb-4 text-gray-300 font-bold rounded-lg">I have a feeling my staff are not working as they should. What can I do?</summary>
				<div class="px-6 pb-6 space-y-2">
					<p>If you allow us we will work with you to ensure you have an effective performance management program. </p> 
					<p>We will help you conduct performance management trainings, objectives setting and periodic performance appraisals including implementation of performance improvement plans.</p>
				</div>
			</details>
		</div>
	</div>
</section>

<section id="testimonials" class="my-8 dark:bg-gray-800 dark:text-gray-300 min-h-screen">
	<div class="container flex flex-col items-center mx-auto mb-12 md:p-10 md:px-12">
		<h1 class="p-4 text-4xl font-semibold leading-10 text-center">What our customers are saying about us</h1>
	</div>
	<div class="container flex flex-col items-center justify-center mx-auto lg:flex-row lg:flex-wrap lg:justify-evenly lg:px-10">
		<div class="flex flex-col max-w-sm mx-4 my-6 shadow-lg">
			<div class="px-4 py-12 rounded-t-lg sm:px-8 md:px-12 dark:bg-gray-900">
				<p class="relative px-6 py-1 text-lg italic text-center dark:text-gray-300">
					<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" fill="currentColor" class="w-8 h-8 dark:text-amber-400">
						<path d="M232,246.857V16H16V416H54.4ZM48,48H200V233.143L48,377.905Z"></path>
						<path d="M280,416h38.4L496,246.857V16H280ZM312,48H464V233.143L312,377.905Z"></path>
					</svg>We partnered with Loka Advisory to improve our recruitment processes, and it's been a game-changer. Their training on recruitment strategies and best practices has helped us identify and hire top talent more efficiently. We're now building stronger teams that drive our company's success
					<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" fill="currentColor" class="absolute right-0 w-8 h-8 dark:text-amber-400">
						<path d="M280,185.143V416H496V16H457.6ZM464,384H312V198.857L464,54.1Z"></path>
						<path d="M232,16H193.6L16,185.143V416H232ZM200,384H48V198.857L200,54.1Z"></path>
					</svg>
				</p>
			</div>
			<div class="flex flex-col items-center justify-center p-8 rounded-b-lg dark:bg-amber-400 dark:text-gray-900">
				<img src="#" alt="" class="bg-black w-16 h-16 mb-2 -mt-16 bg-center bg-cover rounded-full">
				<p class="text-xl font-semibold">Brian Mwasa</p>
				<p class="text-sm uppercase">HR Director</p>
			</div>
		</div>
		<div class="flex flex-col max-w-sm mx-4 my-6 shadow-lg">
			<div class="px-4 py-12 rounded-t-lg sm:px-8 md:px-12 dark:bg-gray-900">
				<p class="relative px-6 py-1 text-lg italic text-center dark:text-gray-300">
					<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" fill="currentColor" class="w-8 h-8 dark:text-amber-400">
						<path d="M232,246.857V16H16V416H54.4ZM48,48H200V233.143L48,377.905Z"></path>
						<path d="M280,416h38.4L496,246.857V16H280ZM312,48H464V233.143L312,377.905Z"></path>
					</svg>The training solutions provided are indeed outstanding. Their approach to employee development has not only improved our team's skills but also increased employee satisfaction. Investing in training has proven to be a vital tool in retaining our valuable talent.
					<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" fill="currentColor" class="absolute right-0 w-8 h-8 dark:text-amber-400">
						<path d="M280,185.143V416H496V16H457.6ZM464,384H312V198.857L464,54.1Z"></path>
						<path d="M232,16H193.6L16,185.143V416H232ZM200,384H48V198.857L200,54.1Z"></path>
					</svg>
				</p>
			</div>
			<div class="flex flex-col items-center justify-center p-8 rounded-b-lg dark:bg-amber-400 dark:text-gray-900">
				<img src="#" alt="" class="bg-black w-16 h-16 mb-2 -mt-16 bg-center bg-cover rounded-full">
				<p class="text-xl font-semibold leadi">Agnes Mbuthia</p>
				<p class="text-sm uppercase">Training manager</p>
			</div>
		</div>
		<div class="flex flex-col max-w-sm mx-4 my-6 shadow-lg">
			<div class="px-4 py-12 rounded-t-lg sm:px-8 md:px-12 dark:bg-gray-900">
				<p class="relative px-6 py-1 text-lg italic text-center dark:text-gray-300">
					<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" fill="currentColor" class="w-8 h-8 dark:text-amber-400">
						<path d="M232,246.857V16H16V416H54.4ZM48,48H200V233.143L48,377.905Z"></path>
						<path d="M280,416h38.4L496,246.857V16H280ZM312,48H464V233.143L312,377.905Z"></path>
					</svg>We were struggling with employee turnover until we engaged Loka Advisory for training on employee retention. Their expert guidance and strategies have significantly reduced attrition rates. Our employees now feel more engaged, valued, and are committed to our organization's success.
					<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" fill="currentColor" class="absolute right-0 w-8 h-8 dark:text-amber-400">
						<path d="M280,185.143V416H496V16H457.6ZM464,384H312V198.857L464,54.1Z"></path>
						<path d="M232,16H193.6L16,185.143V416H232ZM200,384H48V198.857L200,54.1Z"></path>
					</svg>
				</p>
			</div>
			<div class="flex flex-col items-center justify-center p-8 rounded-b-lg dark:bg-amber-400 dark:text-gray-900">
				<img src="#" alt="" class="bg-black w-16 h-16 mb-2 -mt-16 bg-center bg-cover rounded-full">
				<p class="text-xl font-semibold leadi">Magdalene Okwemba</p>
				<p class="text-sm uppercase">Manager, Human capital</p>
			</div>
		</div>
	</div>
</section>

<section id="team" class="py-4 min-h-screen">
	<div class="max-w-screen-xl mx-auto px-4 lg:px-8">
		<div class="max-w-xl mx-auto sm:text-center">
			<!-- <h3 class="text-gray-200 text-4xl font-semibold lg:text-6xl">Our team</h3> -->
			<h1 class="lg:p-4 text-4xl font-semibold leading-10 text-center lg:text-6xl text-gray-300">Our team</h1>
			<p class="text-gray-300 my-4 lg:mt-12">
				At the helm of the organization are professionals with over 50 years of accumulated experience in diverse fields.
			</p>
		</div>
		<div class="lg:px-96 lg:py-14">
			<ul class="grid gap-10 lg:grid-cols-2">
				<li>
					<div class="w-3/4 md:w-full md:h-5/6">
						<img
							src="/renee.jpg"
							class="w-full h-full object-cover object-center shadow-md rounded-md"
							alt="founder - renee"
						/>
					</div>
					<div class="mt-4">
						<h4 class="text-lg text-gray-500 font-semibold">Renee Wachara</h4>
						<!-- <span class="text-[#fbbf24]"> - Founder</span> -->
					</div>
				</li>
				<li class="flex flex-col">
					<div class="w-3/4 md:w-full md:h-5/6">
						<img
							src="/pow-small.jpg"
							class="w-full h-full object-cover object-center shadow-md rounded-md"
							alt="chief operations officer - philemon"
						/>
					</div>
					<div class="mt-4">
						<h4 class="text-lg text-gray-500 font-semibold">Philemon Wachara</h4>
						<!-- <span class="text-[#fbbf24]">- Co-founder</span> -->
					</div>
				</li>
			</ul>
		</div>
	</div>
</section>

<section id="contact" class="bg-slate-800">
    <div class="mx-auto max-w-7xl px-4 py-16 sm:px-6 lg:px-8 lg:py-20">
        <div class="mb-4">
            <div class="mb-6 max-w-3xl text-center sm:text-center md:mx-auto md:mb-12">
                <h2
                    class="font-heading mb-4 font-bold tracking-tight text-gray-200 text-3xl lg:text-5xl">
                    Get in touch<span class="text-[#fbbf24]">!</span>
                </h2>
                <p class="mx-auto mt-4 max-w-3xl text-xl text-gray-400">We are here to help.
                </p>
            </div>
        </div>
        <div class="flex items-stretch justify-center">
            <div class="grid md:grid-cols-2">
                <div class="h-full pr-6">
                    <p class="mt-3 mb-12 text-lg text-gray-600 dark:text-slate-400">
						Reach out to us with your enquiries or needs and we will revert immediately.
                    </p>
                    <ul class="mb-6 md:mb-0">
                        <li class="flex">
                            <div class="flex h-10 w-10 items-center justify-center rounded bg-[#fbbf24] text-gray-900">
                                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
                                    fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" class="h-6 w-6">
                                    <path d="M9 11a3 3 0 1 0 6 0a3 3 0 0 0 -6 0"></path>
                                    <path
                                        d="M17.657 16.657l-4.243 4.243a2 2 0 0 1 -2.827 0l-4.244 -4.243a8 8 0 1 1 11.314 0z">
                                    </path>
                                </svg>
                            </div>
                            <div class="ml-4 mb-4">
                                <h3 class="mb-2 text-lg font-medium leading-6 text-gray-900 dark:text-white">Our Address
                                </h3>
                                <p class="text-gray-600 dark:text-slate-400">P. O. Box 74715</p>
                                <p class="text-gray-600 dark:text-slate-400">City Square</p>
                                <p class="text-gray-600 dark:text-slate-400">Nairobi</p>
                            </div>
                        </li>
                        <li class="flex">
                            <div class="flex h-10 w-10 items-center justify-center rounded bg-[#fbbf24] text-gray-900">
                                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
                                    fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" class="h-6 w-6">
                                    <path
                                        d="M5 4h4l2 5l-2.5 1.5a11 11 0 0 0 5 5l1.5 -2.5l5 2v4a2 2 0 0 1 -2 2a16 16 0 0 1 -15 -15a2 2 0 0 1 2 -2">
                                    </path>
                                    <path d="M15 7a2 2 0 0 1 2 2"></path>
                                    <path d="M15 3a6 6 0 0 1 6 6"></path>
                                </svg>
                            </div>
                            <div class="ml-4 mb-4">
                                <h3 class="mb-2 text-lg font-medium leading-6 text-gray-900 dark:text-white">Contact
                                </h3>
                                <p class="text-gray-600 dark:text-slate-400">Mobile: +254 721 544 724</p>
                                <p class="text-gray-600 dark:text-slate-400">Email: info@loka-advisory.com</p>
                            </div>
                        </li>
                        <li class="flex">
                            <div class="flex h-10 w-10 items-center justify-center rounded bg-[#fbbf24] text-gray-900">
                                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
                                    fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" class="h-6 w-6">
                                    <path d="M3 12a9 9 0 1 0 18 0a9 9 0 0 0 -18 0"></path>
                                    <path d="M12 7v5l3 3"></path>
                                </svg>
                            </div>
                            <div class="ml-4 mb-4">
                                <h3 class="mb-2 text-lg font-medium leading-6 text-gray-900 dark:text-white">Working
                                    hours</h3>
                                <p class="text-gray-600 dark:text-slate-400">Monday - Friday: 08:00 - 17:00</p>
                                <p class="text-gray-600 dark:text-slate-400">Saturday &amp; Sunday: Closed</p>
                            </div>
                        </li>
                    </ul>
                </div>
                <div class="card h-fit max-w-6xl p-5 lg:p-12" id="form">
                    <h2 class="mb-4 text-2xl font-bold">Ready to Get Started?</h2>
                    <form id="contactForm" action="https://formsubmit.co/f10fff0cf0d3a433102464e2c156509a" method="POST">
                        <div class="mb-6">
                            <div class="mx-0 mb-1 sm:mb-4">
                                <div class="mx-0 mb-1 sm:mb-4">
                                    <label for="name" class="pb-1 text-xs uppercase tracking-wider">Name</label>
									<input type="text" id="name" name="name" autocomplete="given-name" class="mb-2 w-full rounded-md border border-gray-400 py-2 pl-2 pr-4 shadow-md bg-gray-400 font-semibold text-black sm:mb-0"required>
                                </div>
                                <div class="mx-0 mb-1 sm:mb-4">
                                    <label for="email" class="pb-1 text-xs uppercase tracking-wider">Email</label>
									<input type="email" id="email" name="email" autocomplete="email" class="mb-2 w-full rounded-md border border-gray-400 py-2 pl-2 pr-4 shadow-md bg-gray-400 font-semibold text-black sm:mb-0" required>
                                </div>
                            </div>
                            <div class="mx-0 mb-1 sm:mb-4">
                                <label for="message" class="pb-1 text-xs uppercase tracking-wider">Message</label>
								<textarea id="message" name="message" cols="30" rows="5" class="mb-2 w-full rounded-md border border-gray-400 py-2 pl-2 pr-4 shadow-md bg-gray-400 font-semibold text-black sm:mb-0" required></textarea>
                            </div>
                        </div>
                        <div class="text-center">
                            <button type="submit" class="w-full bg-[#fbbf24] text-gray-900 font-bold px-6 py-3 font-xl rounded-md sm:mb-0">Send Message</button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
	<footer class="mt-auto w-full max-w-[85rem] py-2 px-4 sm:px-6 lg:px-8 mx-auto">
		<!-- Grid -->
		<hr class="border-slate-200 mb-2">
		<div class="flex flex-row justify-between">
			
			<p class="text-gray-500">© Loka Advisory Services Ltd, <span id="copyright">{ thisYear }</span>. All rights reserved.</p>
			<p class="text-gray-500">
				<a href="https://polo-solutions.com" target="_blank">
					Designed by Polo Solutions Ltd
				</a>
			</p>
		</div>
		<!-- End Grid -->
	</footer>
</section>

<style>

	details[open] summary ~ * {
		animation: sweep 0.3s ease-in-out;
	}

	@keyframes sweep{
		from {
			opacity: 0;margin-top: -10px;
		}
		to {
			opacity: 1;margin-top: 0;
		}
	}

	/* carousel */
.carousel{
    height: 100vh;
    margin-top: -50px;
    width: 100vw;
    overflow: hidden;
    position: relative;
}
.carousel .list .item{
    width: 100%;
    height: 100%;
    position: absolute;
    inset: 0 0 0 0;
}
.carousel .list .item img{
    width: 100%;
    height: 100%;
    object-fit: cover;
}
.carousel .list .item .content{
    position: absolute;
    top: 20%;
    width: 1140px;
    max-width: 80%;
    left: 50%;
    transform: translateX(-50%);
    padding-right: 30%;
    box-sizing: border-box;
    color: #fff;
    text-shadow: 0 5px 10px #0004;
}
.carousel .list .item .author{
    font-weight: bold;
    letter-spacing: 10px;
}
.carousel .list .item .title,
.carousel .list .item .topic{
    font-size: 5em;
    font-weight: bold;
    line-height: 1.3em;
}
.carousel .list .item .topic{
    color: #f1683a;
}
.carousel .list .item .buttons{
    display: grid;
    grid-template-columns: repeat(2, 130px);
    grid-template-rows: 40px;
    gap: 5px;
    margin-top: 20px;
}
.carousel .list .item .buttons button{
    border: none;
    background-color: #eee;
    letter-spacing: 3px;
    font-family: Poppins;
    font-weight: 500;
}
.carousel .list .item .buttons button:nth-child(2){
    background-color: transparent;
    border: 1px solid #fff;
    color: #eee;
}
/* thumbail */
.thumbnail{
    position: absolute;
    bottom: 50px;
    left: 50%;
    width: max-content;
    z-index: 100;
    display: flex;
    gap: 20px;
}
.thumbnail .item{
    width: 150px;
    height: 220px;
    flex-shrink: 0;
    position: relative;
}
.thumbnail .item img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 20px;
}
.thumbnail .item .content{
    color: #fff;
    position: absolute;
    bottom: 10px;
    left: 10px;
    right: 10px;
}
.thumbnail .item .content .title{
    font-weight: 500;
}
.thumbnail .item .content .description{
    font-weight: 300;
}
/* arrows */
.arrows{
    position: absolute;
    top: 80%;
    right: 52%;
    z-index: 100;
    width: 300px;
    max-width: 30%;
    display: flex;
    gap: 10px;
    align-items: center;
}
.arrows button{
    width: 40px;
    height: 40px;
    border-radius: 50%;
    background-color: #eee4;
    border: none;
    color: #fff;
    font-family: monospace;
    font-weight: bold;
    transition: .5s;
}
.arrows button:hover{
    background-color: #fff;
    color: #000;
}

/* animation */
.carousel .list .item:nth-child(1){
    z-index: 1;
}

/* animation text in first item */

.carousel .list .item:nth-child(1) .content .author,
.carousel .list .item:nth-child(1) .content .title,
.carousel .list .item:nth-child(1) .content .topic,
.carousel .list .item:nth-child(1) .content .des,
.carousel .list .item:nth-child(1) .content .buttons
{
    transform: translateY(50px);
    filter: blur(20px);
    opacity: 0;
    animation: showContent .5s 1s linear 1 forwards;
}
@keyframes showContent{
    to{
        transform: translateY(0px);
        filter: blur(0px);
        opacity: 1;
    }
}
.carousel .list .item:nth-child(1) .content .title{
    animation-delay: 1.2s!important;
}
.carousel .list .item:nth-child(1) .content .topic{
    animation-delay: 1.4s!important;
}
.carousel .list .item:nth-child(1) .content .des{
    animation-delay: 1.6s!important;
}
.carousel .list .item:nth-child(1) .content .buttons{
    animation-delay: 1.8s!important;
}
/* create animation when next click */
.carousel.next .list .item:nth-child(1) img{
    width: 150px;
    height: 220px;
    position: absolute;
    bottom: 50px;
    left: 50%;
    border-radius: 30px;
    animation: showImage .5s linear 1 forwards;
}
@keyframes showImage{
    to{
        bottom: 0;
        left: 0;
        width: 100%;
        height: 100%;
        border-radius: 0;
    }
}

.carousel.next .thumbnail .item:nth-last-child(1){
    overflow: hidden;
    animation: showThumbnail .5s linear 1 forwards;
}
.carousel.prev .list .item img{
    z-index: 100;
}
@keyframes showThumbnail{
    from{
        width: 0;
        opacity: 0;
    }
}

/* .carousel.next .thumbnail{
    animation: effectNext .5s linear 1 forwards;
} */

@keyframes effectNext{
    from{
        transform: translateX(150px);
    }
}

/* running time */

.carousel .time{
    position: absolute;
    z-index: 1000;
    width: 0%;
    height: 3px;
    background-color: #f1683a;
    left: 0;
    top: 0;
}

/* .carousel.next .time,
.carousel.prev .time{
    animation: runningTime 3s linear 1 forwards;
} */

@keyframes runningTime{
    from{ width: 100%}
    to{width: 0}
}


/* prev click */

.carousel.prev .list .item:nth-child(2){
    z-index: 2;
}

.carousel.prev .list .item:nth-child(2) img{
    animation: outFrame 0.5s linear 1 forwards;
    position: absolute;
    bottom: 0;
    left: 0;
}
@keyframes outFrame{
    to{
        width: 150px;
        height: 220px;
        bottom: 50px;
        left: 50%;
        border-radius: 20px;
    }
}

.carousel.prev .thumbnail .item:nth-child(1){
    overflow: hidden;
    opacity: 0;
    animation: showThumbnail .5s linear 1 forwards;
}
.carousel.next .arrows button,
.carousel.prev .arrows button{
    pointer-events: none;
}
.carousel.prev .list .item:nth-child(2) .content .author,
.carousel.prev .list .item:nth-child(2) .content .title,
.carousel.prev .list .item:nth-child(2) .content .topic,
.carousel.prev .list .item:nth-child(2) .content .des,
.carousel.prev .list .item:nth-child(2) .content .buttons
{
    animation: contentOut 1.5s linear 1 forwards!important;
}

@keyframes contentOut{
    to{
        transform: translateY(-150px);
        filter: blur(20px);
        opacity: 0;
    }
}
@media screen and (max-width: 678px) {
    .carousel .list .item .content{
        padding-right: 0;
		padding-left: 0;
    }
    .carousel .list .item .content .title{
        font-size: 30px;
    }
}
</style>