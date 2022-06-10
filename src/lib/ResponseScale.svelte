<script>
    import {answers} from "../data/stores.js"

    const values = [0,1,2,3,4,5,6,7]

    let response = null;

    function updateStore(id) {
        let first = id.charAt(0)
        let second = id.charAt(1)
        $answers[first] = 7 - parseInt(response)
        $answers[second] = parseInt(response)
    }
    export let id;
</script>

<form class="response-scale" id={id} >
    {#each values as value}
        <input type="radio" name="likert" bind:group={response} id={id} value={value} on:change={() => updateStore(id)} />
    {/each}
</form>

<style>
    .response-scale {
        display: flex;
        gap: .5rem;
    }
</style>