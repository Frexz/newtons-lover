<script>
    import Card from "./komponenter/Card.svelte";
    import Tabs from "./komponenter/Tabs.svelte";
    import { fade } from "svelte/transition";


    // Tabs
    let tabOverskrifter = ['Newtons 1. lov', 'Newtons 2. lov', 'Newtons 3. lov']
    $: aktivOverskrift = 'Newtons 1. lov'

    function byttTab(e) {
        aktivOverskrift = e.detail
        console.log(aktivOverskrift)
    }

</script>

<main>
    <Tabs {aktivOverskrift} {tabOverskrifter} on:byttTab={byttTab}/>
        {#if aktivOverskrift === 'Newtons 1. lov'}
            <Card>
                <h3>Newtons 1. lov</h3>
                <div class="content">
                    <p class="definisjon">
                        <em>Hvis summen av alle kreftene som virker på en gjenstand er null,
                        er gjenstanden i ro eller beveger seg langs en rett linje med konstant fart.
                        <br><br>
                        Hvis en gjenstand er i ro eller beveger seg langs en rett linje med konstant fart,
                        er summen av alle kreftene som virker på gjenstanden, lik null.</em>
                    </p>
                    <img class="bilde" src="src/img/1.png" alt="Newtons 1. lov">
                    <p class="formel"><em>&#8721;F = 0 &harr v = konstant</em></p>
                </div>
            </Card>
        {:else if aktivOverskrift === 'Newtons 2. lov'}
            <Card>
                <h3>Newtons 2. lov</h3>
                <div class="content">
                    <p class="definisjon">
                        <em>Summen av kreftene som virker på en gjenstand,
                            er lik massen ganget med akselerasjonen.
                        </em>
                    </p>
                    <img class="bilde" src="src/img/2.png" alt="Newtons 2. lov">
                    <p class="formel"><em>&#8721;F = ma</em></p>
                </div>
            </Card>
        {:else if aktivOverskrift === 'Newtons 3. lov'}
            <Card>
                <h3>Newtons 3. lov</h3>
                <div class="content">
                    <p class="definisjon">
                        <em>Når en gjenstand A virker på en gjenstand B med en kraft F,
                        virker det en like stor og motsatt rettet kraft F* fra gjenstand B
                        på gjenstand A. Denne kraften kaller vi motkraften til F.</em>
                    </p>
                    <img class="bilde" src="src/img/3.png" alt="Newtons 3. lov">
                    <p class="formel"><em>F = -F*</em></p>
                </div>
            </Card>
        {/if}
</main>

<style>
    main {
		max-width: 960px;
		margin: 40px auto;
	}

    h3 {
        border-bottom: 2px solid;
        color: #1C6758;
        margin: 0 auto;
        width: 25%;

    }

    .content {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 20px;
        margin-top: 30px;
    }

    .definisjon {
        margin: 0 auto;
        padding: 10px;
    }

    .bilde {
        max-width: 100%;
        margin: 0 auto;
    }

    .formel {
        grid-column-start: 1;
        grid-column-end: 3;
    }
</style>
