<script>
    import Navbar from "../components/Navbar.svelte";
    import Footer from "../components/Footer.svelte";
    import MainCard from "../components/MainCard.svelte";
    import CardsGrid from "../components/CardsGrid.svelte";



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


    const teams = [
        {
            "name": "Team A vs Team B",
            "image": "/images/terrace-unsplash.jpg",  // Image path (you can replace it with an actual image path)
            "description": "Exciting match between Team A and Team B."
        },
        {
            "name": "Team C vs Team D",
            "image": "/images/terrace-unsplash.jpg",
            "description": "A fierce battle between Team C and Team D."
        },
        {
            "name": "Team E vs Team F",
            "image": "/images/terrace-unsplash.jpg",
            "description": "Who will take home the win in this showdown?"
        },
        {
            "name": "Team G vs Team H",
            "image": "/images/terrace-unsplash.jpg",
            "description": "A rivalry match between Team G and Team H."
        },
        {
            "name": "Team I vs Team J",
            "image": "/images/terrace-unsplash.jpg",
            "description": "A nail-biting encounter between Team I and Team J."
        }
    ];

</script>




<Navbar />

    <main class="container mx-auto p-4 flex-grow">
        <h1 class="text-3xl font-bold text-center">Welcome to My Svelte App!</h1>
        <p class="text-gray-700 text-center mt-2">This is a simple homepage.</p>

        <MainCard/>

        <CardsGrid {teams} />

    </main>
<Footer />
