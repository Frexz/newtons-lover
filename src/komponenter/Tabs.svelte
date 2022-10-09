<script>
    import { createEventDispatcher } from "svelte"

    const dispatch = createEventDispatcher()

    export let tabOverskrifter
    export let aktivOverskrift
</script>

<div class="tabs">
    <ul>
        {#each tabOverskrifter as overskrift}
            <li on:click={() => dispatch('byttTab', overskrift)}>
                <div class:aktiv={overskrift === aktivOverskrift}>
                    {overskrift}
                </div>
            </li>
        {/each}
    </ul>
</div>


<style>
    .tabs {
        margin-bottom: 40px;
    }

    ul {
        display: flex;
        justify-content: center;
        padding: 0;
        list-style-type: none;
    }

    li {
        margin: 0 16px;
        font-size: 18px;
        color: #555;
        cursor: pointer;
    }

    .aktiv {
        color: #3D8361;
        border-bottom: 2px solid #3D8361;
        padding-bottom: 8px;
    }
</style>