<script>
    import Navbar from "../components/Navbar.svelte";
    import Footer from "../components/Footer.svelte";

    let message = "Loading...";
    const BACKEND_URL = import.meta.env.VITE_BACKEND_URL;


    async function fetchMessage() {
        console.log('calling from svelete backend:\n')
        try {
            // const res = await fetch("http://localhost:8080/api/hello");
            const res = await fetch(`${BACKEND_URL}`);
            const data = await res.json();
            message = data.message;
        } catch {
            message = "Failed to fetch data.";
            console.error(error);
        }
    }

    fetchMessage();
</script>


<Navbar />

    <main class="container mx-auto p-4 flex-grow">
        <h1 class="text-3xl font-bold text-center">Welcome to My Svelte App!</h1>
        <p class="text-gray-700 text-center mt-2">This is a simple homepage.</p>
    </main>
<Footer />
