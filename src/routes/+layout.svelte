<script>
    import '../app.css';
    /**
     * @typedef {Object} Props
     * @property {import('svelte').Snippet} [children]
     */

    /** @type {Props} */
    let { children } = $props();
</script>

<svelte:head>
	<title>Kresna's Timezone</title>
	<meta name="description" content="Kresna arounds the world! Yeay! ✈️ 🌏" />
</svelte:head>

{@render children?.()}