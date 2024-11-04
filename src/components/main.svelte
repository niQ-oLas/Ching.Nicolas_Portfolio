<script>
    import Step from "./Step.svelte";

    let steps = [
        { name: 'Nicolas Milton Ching Portfolio', icon: 'fa-solid fa-user', href: 'https://example.com/portfolio' },
        { name: 'To-do List', icon: 'fa-solid fa-list-check', href: 'https://example.com/todo' },
        { name: 'My Projects', icon: 'fa-solid fa-diagram-project', href: 'https://example.com/projects' },
    ];

    let benefits = [
        {
            metric: "10x",
            name: "A self-taught developer",
            description: "I taught myself to code using free online resources and fell in love with the creativity and problem-solving involved in developing innovative online experiences."
        },
        {
            name: "A product design & UX fanatic",
            description: "I enjoy crafting and designing amazing user experiences, allowing me to express and experiment with my creativity."
        },
        {
            name: "An excellent communicator",
            description: "I believe in transparency and constructive communication, which helps me develop deep relationships and ensures my effectiveness in any workspace."
        },
    ];
</script>
<main class="flex flex-col flex-1 p-4">
    <section id="introPage" class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14">
        <div class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10">
            <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
                Hi, <span class="Inter text-white-400">my name is</span> <span class="Inter text-yellow-400">Nicolas</span>
                <span class="Inter text-white-400">!</span>
                <br />Tambay <span class="Inter text-white-400">Lamang</span>
            </h2>
            <p class="text-base sm:text-lg md:text-xl">
                My <span class="Inter text-yellow-400">favorite tech</span> includes Svelte, TailwindCSS, & Python!
            </p>
            <a class="blueShadow mx-auto lg:mr-auto text-base sm:text-lg md:text-xl Inter relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950 cursor-pointer"
                href="https://facebook.com/ChingNMC"
                target="_blank" aria-label="Get in touch with Nicolas on Facebook">
                <div class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"></div>
                <h4 class="relative z-9">Get in touch &rarr;</h4>
            </a>
        </div>
        <div class="relative shadow-2xl grid place-items-center">
            <img src={"images/profile.png"} alt="Profile image of Nicolas" class="object-cover" style="z-index: 2; max-height: 70vh;" />
        </div>
    </section>

    <section id="projects" class="py-20 lg:py-32 flex flex-col gap-24">
        <div class="flex flex-col gap-2 text-center">
            <h6 class="text-lg sm:text-xl md:text-2xl">
                To be honest, I’m still learning. This is my first personal project! :D
            </h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
                Curious to see <span class="poppins text-violet-400">my work?</span>
            </h3>
        </div>
        <a href="https://youtu.be/Lrle0x_DHBM?si=A1DAhC_Rh-PFO9S4" target="_blank" 
           class="mx-auto px-4 py-2 rounded-md border border-solid border-white flex items-center gap-2 mb-4 sm:-mb-0 -mt-10 hover:border-violet-700 duration-200"
           aria-label="Watch the introduction video">
            <i class="fa-regular fa-circle-play"></i>
            <p>Watch the video!</p>
        </a>
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
            {#each steps as step}
                <Step step={step} />
            {/each}
        </div>
    </section>
    <section id="about" class="py-20 lg:py-32 flex flex-col gap-24">
        <h2 class="text-center font-semibold text-4xl sm:text-5xl md:text-6xl">
            About Me
        </h2>
        <p class="text-center text-base sm:text-lg md:text-xl">
            I am a passionate developer with a keen interest in creating dynamic and responsive web applications. My journey in tech began with a curiosity for how things work, leading me to explore various programming languages and frameworks.
        </p>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-10">
            {#each benefits as benefit}
                <div class="flex flex-col items-center p-6 border border-gray-300 rounded-lg shadow-md">
                    <h3 class="text-xl font-semibold">{benefit.metric ? benefit.metric + ' ' : ''}{benefit.name}</h3>
                    <p class="text-center mt-2">{benefit.description}</p>
                </div>
            {/each}
        </div>
    </section>
    </main>