<script>
    import MatchCard from "./MatchCard.svelte";
    export let matches
    export let players
</script>

<h3>Matches</h3>
<div class="matches">
    {#each matches as match}
        <MatchCard {match} {players}/>
    {/each}
</div>

<style>
    h3 {
        padding: 0 1rem;
    }
    .matches {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        grid-column-gap: 1rem;
        grid-row-gap: 2rem;
    }
</style>