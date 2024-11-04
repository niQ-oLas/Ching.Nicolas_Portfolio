<script>
    export let y;

    export let tabs = [
        { name: 'Projects', link: '#projects' },
        { name: 'About Me', link: '#aboutme' },
        { name: 'Gallery', link: '#gallery' },
    ];

    let menuOpen = false;
</script>

<header class={'sticky z-[10] top-0 duration-200 px-6 flex items-center justify-between border border-solid ' + (
    y>0? ' py-4 bg-slate-950 border-violet-950' : ' py-6 bg-transparent border-transparent'
)}>
    <h1 class="font-medium">
        <b class="font-bold">Nicolas Milton</b> Ching
    </h1>
    <div class="sm:flex items-center gap-4 hidden md:flex">
        {#each tabs as tab, index}
            <a href={tab.link} class="text-white-400 hover:text-violet-500 duration-200">
                {tab.name}
            </a>
        {/each}
        <a href="https://facebook.com/ChingNMC" target="_blank" class="blueShadow relative overflow-hidden px-5 py-2 group rounded-full bg-white text-slate-950">
            <div class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"></div>
            <h4 class="relative z-9">Get in touch</h4>
        </a>
    </div>
    <button class="sm:flex md:hidden" on:click={() => menuOpen = !menuOpen}>
        <i class="fa-solid fa-bars" />
    </button>
    {#if menuOpen}
        <div class="sm:flex flex-col items-center gap-4 absolute top-full left-0 w-full bg-slate-950 p-4">
            {#each tabs as tab, index}
                <a href={tab.link} class="text-white-400 hover:text-violet-500 duration-200">
                    {tab.name}
                </a>
            {/each}
        </div>
    {/if}
</header>