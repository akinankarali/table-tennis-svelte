<script context="module">
    export async function load({ fetch }) {
        const resMatch = await fetch('../matches.json');
        const resPlayer = await fetch('../players.json');
        const matchData = await resMatch.json();
        const playerData = await resPlayer.json();

        if(resMatch.ok && resPlayer.ok) {
            return {
                props: {
                   matches: matchData,
                   players: playerData,
                }
            }
        }
    }
</script>

<script>
    import Matches from '../components/Matches.svelte';
    export let matches;
    export let players;
</script>

<section>
    <Matches {matches} {players}/>
</section>