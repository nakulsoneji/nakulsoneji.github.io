<script lang="ts">
    import type { LayoutData } from './$types';
    import "$lib/assets/style.css";
    import "../app.css";
    import Navbar from "$lib/components/Navbar.svelte";

    export let data: LayoutData;
</script>

<Navbar />

<slot />
