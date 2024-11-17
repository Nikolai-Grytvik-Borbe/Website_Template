<script lang="ts">
    import Search from "./icons/Search.svelte";

    export let color_mode = "black";
    let background_color = color_mode === "black" ? "bg-[rgba(0,0,0,0.95)]" : "bg-[#e9ecef]";

</script>

<div class="fixed top-0 left-0 h-screen w-screen z-50 {background_color} flex justify-center items-start">
    <div class="mt-[33vh] w-[500px] flex justify-between h-12 m-4 px-4 items-center rounded-2xl border border-gray-700">
        <input type="text" autofocus class="border-none bg-transparent focus:outline-none" placeholder="Enter text" /><p><Search color_mode={color_mode}/></p>
    </div>
</div>