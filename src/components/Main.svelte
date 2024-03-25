<script>
    import Step from "./Step.svelte";
    import Pokedex from './Pokedex.svelte';

    let steps = [
    { name: 'Project', icon: 'fa-solid fa-cart-shopping'},
    { name: 'Ultimate Todos', icon: 'fa-solid fa-list-check'},
    { name: 'Pokédex', icon: 'fa-solid fa-diagram-project', href: 'src/components/Pokedex.svelte'},
    ];

    let benefits= [
        {name: "cultural aware and sensitive", description: "My appreciation for the nuances of diverse cultures is rooted not only in my personal journey as someone who has experienced various domestic environments but also in my academic pursuits in international relations and applied foreign languages. I've gained invaluable insights into the complexities of global cultures." },
        {name: 'skilled interpreter', description: "After studying for a bachelor's degree in applied foreign languages ​​in tourism in English and Spanish, I was able to put my interpreting skills into practice during an internship at an English school. I had the opportunity to interpret for French-speaking, Arabic-speaking, Spanish-speaking, and Turkish-speaking students, thus facilitating communication and fostering an inclusive learning environment." },
        {name: 'creative', description: 'I have a deep passion for the arts, including drawing, painting, sketching, and calligraphy. These creative activities not only allow me to express my imagination but also enhance my attention to detail and patience. In addition to my artistic interests, I am an avid reader with a penchant for exploring a diverse range of books. I believe that these interests contribute to my versatile nature and my ability to approach challenges with creativity and an open mind.' },
    ]
</script>

<main class="flex flex-col flex-1 p-4">
    <section id="introPage" class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14">
        <div class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10">
            <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
                Hi! I'm <span class="poppins text-violet-400">Sabrine</span> Belfakir <br/>Full Stack <span class="poppins text-violet-400">Developer</span>
            </h2>
            <p class="text-base sm:text-lg md:text-xl">
                My <span class="text-violet-400">favorite tech</span> includes HTML, CSS, JavaScript, SQL and Python.
            </p>
            <a href="https://www.linkedin.com/feed/" target="_blank" class="blueShadow mx-auto lg:mr-auto lg:ml-0 text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950 cursor-pointer">
                <div class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"/>
                <h4 class="relative z-9">Get in touch &rarr;</h4>
            </a>
        </div>
        <div class="relative shadow-2xl grid place-items-center">
            <img src={"images/profile.jpg"} alt="Profile" class="object-cover z-[2] mx-h-[70vh]"/>
        </div>
    </section>

    <section class="py-20 lg:py-32 flex flex-col gap-24" id="projects">
        <div class="flex flex-col gap-2 text-center">
            <h6 class="text-large sm:text-xl md:text-2xl">
                A few of my creative endeavors.
            </h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
                Curious to <span class="poppins text-violet-400">see</span> my work?
            </h3>
        </div>
        <a
            href="https://www.youtube.com/watch?v=dQw4w9WgXcQ"
            target="_blank"
            class="mx-auto px-4 py-2 rounded-md border border-solid border-white flex items-center gap-2 -mb-4 sm:-mb-0 -mt-10 hover:border-violet-700 duration-200"
        >
            <i class="fa-regular fa-circle-play" />
            <p>Watch the video</p>
        </a>
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
            <Step step={steps[0]}>
                <p>
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Sint blanditiis ipsam unde eligendi repellendus fugiat reprehenderit, quo animi, ipsum,  <strong
                    class="text-violet-400">vel deserunt consequatur in sequi porro aut. Soluta aliquam quas saepe.</strong> Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sed maiores laudantium, repellat vel, et dolore totam maxime iusto, fugit itaque asperiores nemo. Odit ullam et ex, aliquid consectetur aliquam ipsum.
                </p>
            </Step>
            <Step step={steps[1]}>
                <p>
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Sint blanditiis ipsam unde eligendi repellendus fugiat reprehenderit, quo animi, ipsum,  <strong
                    class="text-violet-400">vel deserunt consequatur in sequi porro aut. Soluta aliquam quas saepe.</strong> Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sed maiores laudantium, repellat vel, et dolore totam maxime iusto, fugit itaque asperiores nemo. Odit ullam et ex, aliquid consectetur aliquam ipsum.
                </p>
            </Step>
            <Step step={steps[2]}>
                <p>
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Sint blanditiis ipsam unde eligendi repellendus fugiat. 
                </p>
                <div class="absolute right-60 top-50">
                    <Pokedex />
                </div>                
            </Step>
        </div>
    </section>
    <section    
        id="about"
        class="py-20 pt-10 lg:pt-16 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative"
        >
        
        <div 
        class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4"
        >
        <h6 
        class="text-lg sm:text-xl md:text-2xl">Want to know more?
        </h6>
        <h3 
        class="font-semibold text-3xl sm:text-4xl md:text-5xl">A bit <span class="poppins text-violet-400">about </span>me.
        </h3>
        </div>
        <p class="mx-auto poppins font-semibold text-lg sm:text-xl md:text-2xl">I am...</p>
        <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
            {#each benefits as benefits, index}
        <div class="flex gap-6 sm:gap-8">
            <p class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold">
                0{index+1}
            </p>
            <div class="flex flex-col gap-6 sm:-gap-8">
                <h3 class="text-2xl sm:text-3xl md:text-5xl">
                  {benefits.name}  
                </h3>
                <p>{benefits.description}</p>
            </div>
        </div>
        {/each}
        </div>
        <h5 class="text-2xl sm:text-3xl font-semibold text-center poppins">The <span class="text-violet-400 poppins">Complete</span> Package</h5>
        <div class="flex flex-col overflow-x-scroll gap-10 max-x[800px] mx-auto w-full">
            <table class="bg-white text-slate-700 rounded text-center">
                <thead class="border-b border-solid boder-slate-200">
                    <tr class="">
                        <th></th>
                        <th class="whitespace-nowrap p-2 px-4">Candidate 1</th>
                        <th class="whitespace-nowrap p-2 px-4">Candidate 2</th>
                        <th class="whitespace-nowrap p-2 px-4">Candidate 3</th>
                        <th class="whitespace-nowrap bg-violet-700 text-white p-4 px-8">Me</th>
                    </tr>
                </thead>
                <tbody>
                <tr class="border-b border-solid    border-slate-200">
                    <td
                    class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap"
                    >Dedication</td>
                    <td><i class="fa-solid fa-xmark text-slate-500"></i></td>
                    <td><i class="fa-solid fa-check text-green-500"></i></td>
                    <td><i class="fa-solid fa-check text-green-500"></i></td>
                    <td><i class="fa-solid fa-check text-green-500"></i></td>
                </tr>
                <tr class="border-b border-solid    border-slate-200">
                    <td
                    class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap"
                    >Riguor</td>
                    <td><i class="fa-solid fa-check text-green-500"></i></td>
                    <td><i class="fa-solid fa-check text-green-500"></i></td>
                    <td><i class="fa-solid fa-check text-green-500"></i></td>
                    <td><i class="fa-solid fa-check text-green-500"></i></td>
                </tr>
                <tr class="border-b border-solid    border-slate-200">
                    <td
                    class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap"
                    >Patience</td>
                    <td><i class="fa-solid fa-check text-green-500"></i></td>
                    <td><i class="fa-solid fa-xmark text-slate-500"></i></td>
                    <td><i class="fa-solid fa-xmark text-slate-500"></i></td>
                    <td><i class="fa-solid fa-check text-green-500"></i></td>
                </tr>
                <tr class="border-b border-solid    border-slate-200">
                    <td
                    class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap"
                    >Polyglote</td>
                    <td><i class="fa-solid fa-xmark text-slate-500"></i></td>
                    <td><i class="fa-solid fa-check text-green-500"></i></td>
                    <td><i class="fa-solid fa-xmark text-slate-500"></i></td>
                    <td><i class="fa-solid fa-check text-green-500"></i></td>
                </tr>
                </tbody>
            </table>
        </div>
        <div class="mx-auto -mt-12 italic sm:hidden pacity-50">
            <p>Scroll to see more &rarr;</p>
        </div>
        <p class="mx-auto">So why not invest?</p>
    </section>
</main>
