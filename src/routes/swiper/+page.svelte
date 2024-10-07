<!-- const images = ["https://images.unsplash.com/photo-1720048171080-78849cff8b19?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxmZWF0dXJlZC1waG90b3MtZmVlZHwxfHx8ZW58MHx8fHx8","https://plus.unsplash.com/premium_photo-1677560517139-1836389bf843?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHwyfHx8ZW58MHx8fHx8"]; -->

<script>
    import { onMount } from 'svelte';
    import Swiper from 'swiper';
    import { Navigation, Pagination, Autoplay } from 'swiper/modules';
  
    import 'swiper/css';
    import 'swiper/css/navigation';
    import 'swiper/css/pagination';
  
    // import Img1 from '../images/Pwhite/PwhiteModel.png';
    // import Img2 from '../images/Iceblue/IceblueModel.png';
    // import Img3 from '../images/DesertBrown/DesertBrownModel.png';
    // import Img4 from '../images/Coppersilk/CopperSilkModel.png';
    // import Img5 from '../images/Norsaragreen/NorsaraGreenModel.png';
    // import Img6 from '../images/Jirawal/JirawalWhiteModel.png';
    // import Img7 from '../images/Zbrown/ZbrownModel.png';
    // import Img8 from '../images/Kharadacream/KhardaCreamModel.png';
    // import Img9 from '../images/Kharadared/KhardaRedModel.png';
    // import Stand from '../images/stand.png';
  
    const images = ["https://images.unsplash.com/photo-1720048171080-78849cff8b19?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxmZWF0dXJlZC1waG90b3MtZmVlZHwxfHx8ZW58MHx8fHx8","https://plus.unsplash.com/premium_photo-1677560517139-1836389bf843?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHwyfHx8ZW58MHx8fHx8","https://unsplash.com/photos/two-glasses-of-wine-with-cherries-on-a-table-ZByCF-zdeRs","https://unsplash.com/photos/two-glasses-of-wine-with-cherries-on-a-table-ZByCF-zdeRs"];
  
    let swiperContainer;
  
    onMount(() => {
      const swiper = new Swiper(swiperContainer, {
        modules: [Navigation, Pagination, Autoplay],
        slidesPerView: 1,
        spaceBetween: 30,
        loop: true,
        autoplay: {
          delay: 3000,
          disableOnInteraction: false,
        },
        pagination: {
          el: '.swiper-pagination',
          clickable: true,
        },
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
        breakpoints: {
          640: {
            slidesPerView: 2,
            spaceBetween: 20,
          },
          768: {
            slidesPerView: 3,
            spaceBetween: 30,
          },
        },
      });
  
      return () => {
        swiper.destroy();
      };
    });
  </script>
  
  <div class="home mt-24 md:mt-10 min-h-screen">
    <div class="main pt-2 container mx-auto px-4">
      <div class="hero w-full flex flex-col-reverse lg:flex-row gap-8">
        <!-- Right div (Carousel) -->
        <div class="right w-full lg:w-1/2 order-2 lg:order-2">
          <div class="slider relative">
            <div class="swiper-container" bind:this={swiperContainer}>
              <div class="swiper-wrapper">
                {#each images as img, index}
                  <div class="swiper-slide">
                    <img src={img} alt={`Granite Slab ${index + 1}`} class="w-full h-auto object-cover rounded-lg shadow-md" />
                  </div>
                {/each}
              </div>
              <div class="swiper-pagination"></div>
              <div class="swiper-button-prev"></div>
              <div class="swiper-button-next"></div>
            </div>
            <!-- <img class="w-full mt-4" src={Stand} alt="Stand for images" /> -->
          </div>
        </div>
        
        <!-- Left div (Content) -->
        <!-- <div class="left w-full lg:w-1/2 order-1 lg:order-1 flex justify-center items-start flex-col gap-4">
          <h1 class="font-mono font-bold text-3xl md:text-4xl text-gray-800">GRANITE SLABS</h1>
          <p class="font-lato text-lg text-gray-600 leading-relaxed">
            We are proud to offer an extensive range of granite colors, originating from the scenic Jalore region of Rajasthan. Our granite comes in various shades, patterns, and finishes, each one meticulously crafted to meet your specific needs. We take pride in providing high-quality products that are both aesthetically pleasing and durable, all while being competitively priced.
          </p>
          <button class="w-32 h-12 bg-green-500 hover:bg-green-600 text-white font-bold rounded-md cursor-pointer transition duration-300 ease-in-out transform hover:scale-105">
            Shop now
          </button>
        </div> -->
      </div>
    </div>
  </div>
  
  <style>
    :global(.swiper-button-next),
    :global(.swiper-button-prev) {
      color: #22c55e; /* green-500 */
    }
  
    :global(.swiper-pagination-bullet-active) {
      background-color: #22c55e; /* green-500 */
    }
  </style>