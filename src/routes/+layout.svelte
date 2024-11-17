<script lang="ts">
	import { onMount } from 'svelte';
	import '../app.css';
	import Searchbar from '../components/Searchbar.svelte';
	import Navbar from '../components/Navbar.svelte';
	let { children } = $props();

	let search = $state(false);
	let color_mode = "black";

	function handleKeydown(event: KeyboardEvent) {
		if (event.key === "Escape" || event.key === "Enter") {
			search = !search; // Toggle the variable
		}
	}

	onMount(() => {
		document.addEventListener("keydown", handleKeydown);
		return () => document.removeEventListener("keydown", handleKeydown);
	});

	$effect(() => {
		// Disable scrolling when `search` is true
		if (search) {
			document.body.style.overflow = 'hidden';
		} else {
			document.body.style.overflow = 'auto';
		}
	})
</script>

<div class={color_mode === "black" 
		? "bg-gradient-to-b from-black via-gray-900 to-black text-white w-screen h-screen"
		: "bg-gradient-to-b from-[#f8f9fa] via-[#e9ecef] to-[#f8f9fa] text-black w-screen h-screen"
	}>

<!-- CONTAINER -->
	<div class="max-w-[1140px] mx-auto">
		{#if search}
			<Searchbar />
		{:else}
			<Navbar color_mode={color_mode} />
		{/if}
		<div class="pt-40 px-8">
			{@render children()}

		</div>

	</div>
</div>
