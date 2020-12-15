<script>
	import router from "page";
	import Home from "./pages/Home.svelte";
	import About from "./pages/About.svelte";
	import Contact from "./pages/Contact.svelte";
	import Donation from "./pages/Donation.svelte";
	import NotFound from "./pages/NotFound.svelte";

	// page akan berubah sesuai page yang diakses
	let page, params;

	// router is for setting SPA
	router("/", () => (page = Home));
	router("/about", () => (page = About));
	router("/contact", () => (page = Contact));
	router(
		"/donation/:id",
		(ctx, next) => {
			params = ctx.params;
			// next to go to page
			next();
		},
		() => (page = Donation)
	);
	// notFound page harus ditaroh paling bawah
	router("/*", () => (page = NotFound));

	// start router
	router.start();
</script>

<!-- set svelte to render component -->

<svelte:component this={page} {params} />
