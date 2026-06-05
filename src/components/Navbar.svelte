<script>
    import { onMount } from 'svelte';
     export let menu_open;
     let y = 0;
    let pageHeight = 10;
    let dropdownOpen = false; // Dropdown state
    let dropdownOpensm = false; // Dropdown state
  
     // onMount(() => {
    //   pageHeight = window.innerHeight * 1.1; // Set pageHeight to double the window height
    // });
     $: scrolled = y > pageHeight;
     function findPos(obj) {
      var curtop = 0;
      if (obj.offsetParent) {
        do {
          curtop += obj.offsetTop;
        } while (obj = obj.offsetParent);
        return curtop;
      }
    }
    const handleCyclo = (e) => {
        e.preventDefault()
        let button = e.target.closest('[data-target]');
        let target = button.getAttribute('data-target');
        let offset = button.getAttribute('data-offset');
        
        window.scroll({
          left:0,
          top:findPos(document.getElementById(target))-offset, 
          behavior:'smooth'
        });
    
        
        
      }
  

  

function openDropdown() {
  dropdownOpen = true;
}

function closeDropdown() {
  dropdownOpen = false;
}
  
    const toggleDropdownsm = () => {
      dropdownOpensm = true;
    };
  
    const closeDropdownsm = () => {
      dropdownOpensm = false;
    };
  
  </script>
  
  <svelte:window bind:scrollY={y}/>
  
    <div id="navbar"  class="fixed space-x-4  md:space-x-0 min-h-fit w-screen sm:min-h-0  left-0
   flex sm:items-center
    ease-in-out transition-all transform duration-300
    z-50  py-4
           {scrolled ? 'bg-white top-0 shadow-md' : 'bg-white text-black '}


   ">
    <div class="w-full md:px-20 px-10 mx-auto  flex justify-between">
     <div class=" md:px-2 m-0 font-medium gap-2 w-fit p-0 rounded-md flex items-center justify-center ">
     
        <a href="/" >
          <img
          src="{scrolled ? '/img/logo.svg' : '/img/logo.svg'}"
          alt="logo"
          class="items-center justify-center  h-12"
        />
      </a>
     </div>
  
     <main class=" flex  items-start px-7 my-auto">
        <div style="font-family: Museo-Sans, sans-serif;" class="flex my-auto  {scrolled?'':''}">
            <div style="font-family: Museo-Sans, sans-serif;" class="flex items-center my-auto">

    <a href="https://business.startupmission.in/" class="hidden md:flex px-6 py-3 text-[16px] font-medium hover:text-[#FD226A]">
        Home
    </a>

    <a href="https://business.startupmission.in/demoday" class="hidden md:flex px-6 py-3 text-[16px] font-medium hover:text-[#FD226A]">
        Big Demo Day
    </a>

    <a href="https://business.startupmission.in/demoday" class="hidden md:flex px-6 py-3 text-[16px] font-medium hover:text-[#FD226A] underline decoration-pink-500 decoration-2">
        BRIDGE
    </a>
    
    <!-- Corporate Innovation Dropdown -->
    <div class="relative hidden md:block group">
        <button
            class="px-6 py-3 text-[16px] font-medium hover:text-[#FD226A]"
        >
            Corporate Innovation
        </button>

        <div
            class="absolute top-full left-1/2 -translate-x-1/2 mt-4
                   w-[340px]
                   bg-white
                   rounded-[24px]
                   shadow-[0_10px_40px_rgba(0,0,0,0.15)]
                   py-4
                   opacity-0 invisible
                   group-hover:opacity-100
                   group-hover:visible
                   transition-all duration-200
                   z-50"
        >
            <a
                href="https://business.startupmission.in/industry_cohort"
                class="block px-8 py-2 text-[16px] text-gray-800 hover:bg-gray-50"
            >
                ME Industry Cohort
            </a>

            <a
                href="https://business.startupmission.in/console/nasscom"
                class="block px-8 py-2 text-[16px] text-gray-800 hover:bg-gray-50"
            >
                NASSCOM Corporate Demand Week
            </a>

            <a
                href="/https://business.startupmission.in/console/kaspersky"
                class="block px-8 py-2 text-[16px] text-gray-800 hover:bg-gray-50"
            >
                Kaspersky Tech Challenge
            </a>

            <a
                href="https://business.startupmission.in/hitachi"
                class="block px-8 py-2 text-[16px] text-gray-800 hover:bg-gray-50"
            >
                Hitachi KSUM Innovation Challenge
            </a>

            <a
                href="https://business.startupmission.in/nic"
                class="block px-8 py-2 text-[16px] text-gray-800 hover:bg-gray-50"
            >
                National Innovation Challenge
            </a>

            <a
                href="https://business.startupmission.in/crompton"
                class="block px-8 py-2 text-[16px] text-gray-800 hover:bg-gray-50"
            >
                Crompton Innovation Challenge
            </a>
        </div>
    </div>

    <a href="#contact" class="hidden md:flex px-6 py-3 text-[16px] font-medium hover:text-[#FD226A]">
        Contact
    </a>

    <a href="https://business.startupmission.in/console/login" class="hidden md:flex px-6 py-3 text-[16px] font-medium hover:text-[#FD226A]">
        Login
    </a>

</div>
        </div>
      
        <div class="flex  items-center justify-center  bg-white my-auto spl_cursor md:hidden flex ">   
             <div on:click="{()=> menu_open = !menu_open }" class="z-50 items-center justify-center my-auto spl_cursor md:pt-4 pt-1   absolute cursor-pointer top-3 md:right-8 right-4 w-10 h-10 md:text-xl text-xs ml-auto transition duration-150  py-1  -solid -transparent rounded bg-transparent block outline-none focus:outline-none" type="button">
                <div class="block absolute w-6 h-0.5 rounded-sm bg-black top-5  duration-500 { menu_open ? 'opacity-0':'' }" ></div>
                <div class="block absolute w-6 h-0.5 rounded-sm bg-black top-6 duration-500 { menu_open ? 'transform rotate-45':'' }"></div>
                <div class="block absolute w-6 h-0.5 rounded-sm bg-black top-7 duration-500 { menu_open ? 'transform -rotate-45':'' }"></div>
                <div class="block absolute w-6 h-0.5 rounded-sm bg-black top-8 duration-500 { menu_open ? 'opacity-0':'' }" ></div>
            </div>
        </div>
    </main>
   </div>
   </div>
  
  
   <div id="navbar" class=" min-h-screen   h-20 p-8 sm:py-3 bg-white left-0 top-0
   flex items-center
    ease-in-out transition-all transform duration-300
   -translate-x-full  fixed z-50
    {menu_open?'translate-x-0':''}
   ">
     <div class="flex bg-white top-4 absolute spl_cursor">   
        <button on:click="{()=> menu_open = !menu_open }" class="z-50 spl_cursor bg-white cursor-pointer fixed right-5 w-10 h-10 text-xl ml-auto transition duration-150 leading-none px-2 py-1  -solid -transparent rounded bg-transparent block outline-none focus:outline-none" type="button">
            <span class="block spl_cursor absolute w-6 h-1 rounded-sm bg-black top-3 duration-500 { menu_open ? 'opacity-0':'' }" ></span>
            <span class="block spl_cursor absolute w-6 h-1 rounded-sm bg-black duration-500 { menu_open ? 'transform rotate-45':'' }"></span>
            <span class="block spl_cursor absolute w-6 h-1 rounded-sm bg-black duration-500 { menu_open ? 'transform -rotate-45':'' }"></span>
            <span class="block spl_cursor absolute w-6 h-1 rounded-sm bg-black bottom-2.5 duration-500 { menu_open ? 'opacity-0':'' }"></span>
        </button>
    </div>
  
  
    <div class="w-fit md:px-20 px-10 mx-auto sm:items-center sm:justify-between">
        <div class="mb-8 gap-2  font-medium sm:bg-transparent p-5 sm:p-0 rounded-md flex items-center justify-center">
            <img src="/img/logo.svg" alt="logo" class="md:h-14 h-12">
  
        </div>
         <nav>
           <ul class="md:text-sm gap-2 font-data">

    <li on:click={() => menu_open = !menu_open}
        class="px-5 py-2 hover:bg-gray-100 md:hidden flex">
        <a href="https://business.startupmission.in/" class="font-bold uppercase">Home</a>
    </li>

    <li on:click={() => menu_open = !menu_open}
        class="px-5 py-2 hover:bg-gray-100 md:hidden flex">
        <a href="https://business.startupmission.in/demoday" class="font-bold uppercase">
            Big Demo Day
        </a>
    </li>

    <!-- Corporate Innovation Dropdown -->
    <li class="px-5 py-2 md:hidden">

        <details class="group">

            <summary
                class="font-bold uppercase cursor-pointer flex items-center justify-between list-none"
            >
                Corporate Innovation

                <svg
                    class="w-4 h-4 transition-transform group-open:rotate-180"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                >
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M19 9l-7 7-7-7"
                    />
                </svg>
            </summary>

            <div class="mt-3 ml-4 flex flex-col border-l-2 border-gray-200">

                <a
                    href="https://business.startupmission.in/industry_cohort"
                    class="py-3 pl-4 text-sm"
                    on:click={() => menu_open = false}
                >
                    ME Industry Cohort
                </a>

                <a
                    href="https://business.startupmission.in/console/nasscom"
                    class="py-3 pl-4 text-sm"
                    on:click={() => menu_open = false}
                >
                    NASSCOM Corporate Demand Week
                </a>

                <a
                    href="/https://business.startupmission.in/console/kaspersky"
                    class="py-3 pl-4 text-sm"
                    on:click={() => menu_open = false}
                >
                    Kaspersky Tech Challenge
                </a>

                <a
                    href="https://business.startupmission.in/hitachi"
                    class="py-3 pl-4 text-sm"
                    on:click={() => menu_open = false}
                >
                    Hitachi KSUM Innovation Challenge
                </a>

                <a
                    href="https://business.startupmission.in/nic"
                    class="py-3 pl-4 text-sm"
                    on:click={() => menu_open = false}
                >
                    National Innovation Challenge
                </a>

                <a
                    href="https://business.startupmission.in/crompton"
                    class="py-3 pl-4 text-sm"
                    on:click={() => menu_open = false}
                >
                    Crompton Innovation Challenge
                </a>

            </div>
        </details>

    </li>

    <li on:click={() => menu_open = !menu_open}
        class="px-5 py-2 hover:bg-gray-100 md:hidden flex">
        <a href="#contact" class="font-bold uppercase">
            Contact
        </a>
    </li>

    <li on:click={() => menu_open = !menu_open}
        class="px-5 py-2 hover:bg-gray-100 md:hidden flex">
        <a href="https://business.startupmission.in/console/login" class="font-bold uppercase">
            Login
        </a>
    </li>

</ul>
        </nav>
    </div>
  
  </div>
  
  
  
  