<script lang="ts">
	import NGB from './icons/NGB.svelte';
    import Hamburger from './icons/Hamburger.svelte';
    import Cross from './icons/Cross.svelte';
    import Search from './icons/Search.svelte';
    export let color_mode = "black";

    let color = color_mode === "black" ? "white" : "black";
    let size = 24;

    let toggle_hamburger = false;
    let search = false;

    let color_bg = color_mode === "black" ? "bg-black" : "bg-white";
    let color_text = color_mode === "black" ? "text-white" : "text-black";

</script>

<div class="block md:hidden">
  <!-- Mobile Navbar -->
    <div class="fixed w-full">
        <div class="flex justify-between h-12 m-4 px-4 items-center rounded-2xl border border-gray-700">
            <div><NGB color_mode={color_mode}/></div>
            <button on:click={() => toggle_hamburger = !toggle_hamburger}>
                <Hamburger size={size} color_mode={color_mode}/>
            </button>
        </div>
    </div>
    {#if toggle_hamburger}
        <div class="{color_bg} {color_text} fixed top-0 right-0 h-full w-72 z-50 shadow-lg border-l border-gray-700">
            <button
                on:click={() => toggle_hamburger = !toggle_hamburger} class="p-4 text-white absolute top-0 right-0">
                <Cross size={size} color_mode={color_mode} />
            </button>

            <ul class="pt-20 pl-6">
                <div class="py-4 hover:opacity-90 transition-all"><a href="#home">Home</a></div>
                <div class="pr-6">
                    <hr>
                </div>
                <div class="py-4 hover:opacity-90 transition-all"><a href="#contact">Contact</a></div>
            </ul>
        </div>
    {/if}

</div>

<div class="hidden md:block">
  <!-- Desktop Navbar -->
    <div class="fixed max-w-[1140px] w-full">
        <div class="flex justify-between h-12 m-4 px-4 items-center rounded-2xl border border-gray-700">
            <div class="hover:opacity-90 transition-all cursor-pointer">
                <a href="/">
                    <NGB color_mode={color_mode}/>
                </a>
            </div>
            <div class="flex items-center gap-8 text-md">
                <div class="hover:opacity-90 transition-all"><a href="#home">Home</a></div>
                <div class="hover:opacity-90 transition-all"><a href="#contact">Contact</a></div>
            </div>
        </div>
    </div>
</div>