<script>
    import Header from "../components/Header.svelte";
    import Welcome from "../components/Welcome.svelte";
    import CharityLists from "../components/CharityLists.svelte";
    import Promo from "../components/Promo.svelte";
    import Footer from "../components/Footer.svelte";

    // dummy data
    import { charities } from "../data/charity";
</script>

<Header />
<Welcome />
<CharityLists {charities} />
<Promo />
<Footer />
