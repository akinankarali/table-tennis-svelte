<script>
    export let match;
    export let players;
</script>

<div class="match-card">
    <div class="player-1">
        {#each players as player}
            {#if player.id === match.matchPlayers[0].playerId}
                <h2>{player.playerName}</h2>
                <p>{match.matchPlayers[0].score}</p>
            {/if}
        {/each}
    </div>
    <img src="../table.png" alt="table">
    <div class="player-2">
        {#each players as player}
            {#if player.id === match.matchPlayers[1].playerId}
                <h2>{player.playerName}</h2>
                <p>{match.matchPlayers[1].score}</p>
            {/if}
        {/each}
    </div>
    <div class="match-details">
        <h3>{match.matchType}</h3>
    </div>
</div>

<style>
    img {
        width: 100%;
        height: 30vh;
        object-fit: cover;
        border-radius: 1rem;
        margin-bottom: 1rem;
    }
    h2 {
        font-size: 0.9rem;
        padding-right: 1rem;
    }
    .player-2, .player-1{
        height: 5vh;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .match-card {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        padding: 1rem;
    }
    .match-details {
        position: relative;
        top: -16rem;
        left: 2.6rem;
        font-size: 0.8rem;
        color: white;
        display: flex;
        align-items: center;
    }
</style>