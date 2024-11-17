<script lang="ts">
    export let size: number = 40;
    export let color_mode: string = "black";
    let color = color_mode === "black" ? "white" : "black";
</script>

<svg width="{size}px" height="{size}px" class="cursor-pointer" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M4 18L20 18" stroke="{color}" stroke-width="2" stroke-linecap="round"/>
<path d="M4 12L20 12" stroke="{color}" stroke-width="2" stroke-linecap="round"/>
<path d="M4 6L20 6" stroke="{color}" stroke-width="2" stroke-linecap="round"/>
</svg>