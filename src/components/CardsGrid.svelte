<!-- src/components/CardsGrid.svelte -->
<script>
    export let teams = []; // This will be passed in as a prop (JSON object)
</script>

<div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
    {#each teams as team}
        <div class="bg-white p-4 rounded-lg shadow-lg">
            <img src={team.image} alt={team.name} class="rounded-lg w-full h-40 object-cover mb-4">
            <h3 class="text-xl font-semibold">{team.name}</h3>
            <p class="text-gray-700">{team.description}</p>
            <div class="mt-2 text-center">
                <button class="bg-blue-500 text-white py-1 px-4 rounded-lg hover:bg-blue-600">
                    View Match
                </button>
            </div>
        </div>
    {/each}
</div>

<style>
    /* You can customize the card layout further here */
</style>
