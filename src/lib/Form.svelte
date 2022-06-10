<script>
    import ResponseScale from "./ResponseScale.svelte";
    import {answers} from "../data/stores.js";

</script>

<form>
    <h1>DiSC Personality Quiz</h1> 
    <div class="form-option">
        <p>Results-Oriented</p>
        <ResponseScale id="AB" />
        <p>Human Contact-Oriented</p>
    </div>
    <div class="form-option">
        <p>Extroverted</p>
        <ResponseScale id="CD" />
        <p>Introverted</p>
    </div>
    <div class="form-option">
        <p>Emotions</p>
        <ResponseScale id="EF" />
        <p>Logic</p>
    </div>
    <div class="form-option">
        <p>Action-Oriented</p>
        <ResponseScale id="GH" />
        <p>Thinking-Oriented</p>
    </div>
    <div class="form-option">
        <p>Handling Conflicts</p>
        <ResponseScale id="IJ" />
        <p>Avoiding Conflicts</p>
    </div>
    <div class="form-option">
        <p>Control</p>
        <ResponseScale id="KL" />
        <p>Instinct</p>
    </div>
    <!-- <div class="answer-pool">
        <p>D: {$answers.A + $answers.G + $answers.I}</p>
        <p>I: {$answers.B + $answers.C + $answers.L}</p>
        <p>S: {$answers.D + $answers.E + $answers.J}</p>
        <p>C: {$answers.F + $answers.H + $answers.K}</p>
    </div> -->
</form>

<style>
    form {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .answer-pool {
        display: flex;
        gap: 1rem;
    }
    .form-option {
        display: grid;
        grid-template-columns: 1fr auto 1fr;
        gap: 1rem;
        align-items: center;
    }
    .form-option > *:first-child {
        text-align: right;
    }
    .form-option > *:last-child {
        text-align: left;
    }
</style>