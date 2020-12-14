<script>
	import router from "page";
	import Home from "./pages/Home.svelte";
	import About from "./pages/About.svelte";
	import Contact from "./pages/Contact.svelte";

	// page akan berubah sesuai page yang diakses
	let page;

	// router is for setting SPA
	router("/", () => (page = Home));
	router("/about", () => (page = About));
	router("/contact", () => (page = Contact));

	// start router
	router.start();
</script>

<!-- set svelte to render component -->

<svelte:component this={page} />
