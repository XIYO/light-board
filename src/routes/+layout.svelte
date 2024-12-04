<script>
	import '$lib/style.css';
	const { children } = $props();

	export const prerender = true;
</script>

{@render children()}
