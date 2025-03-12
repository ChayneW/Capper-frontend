<script>
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

<h1>{message}</h1>
