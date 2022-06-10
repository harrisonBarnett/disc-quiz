<script>
    import {answers} from "../data/stores.js"
    import {onMount} from "svelte"
    import {Chart, registerables} from "chart.js"
    Chart.register(...registerables)
    onMount(async ()=> {})

    function renderChart() {
        var ctx = document.querySelector(".chart").getContext("2d");
        var chart = new Chart(ctx, {
            type: "pie",
            data: {
                labels: ["Dominance", "Influence", "Conscientiousness", "Steadiness"],
                datasets: [
                    {
                    label: "My data",
                    backgroundColor: [
                    'rgba(255, 99, 132, 0.2)',
                    'rgba(255, 159, 64, 0.2)',
                    'rgba(255, 205, 86, 0.2)',
                    'rgba(75, 192, 192, 0.2)'],
                    borderColor: "rgb(0,0,0)",
                    data:[
                        ($answers.A + $answers.G + $answers.I),
                        ($answers.B + $answers.C + $answers.L), 
                        ($answers.F + $answers.H + $answers.K),
                        ($answers.D + $answers.E + $answers.J)]     
                    }
                ]
            },
            options: {
                responsive: true
            }
        })
    }

</script>

<div class="graph-container">
    <button on:click={renderChart}>View Your Results</button>

    <div class="chart-container"
    style="position: relative; height: 25vmax; width: 25vmax;">
        <canvas class="chart"></canvas>
    </div>
</div>

<style>
    .graph-container {
        display: flex;
        flex-direction: column;
        gap: 2rem;
        align-items: center;
    }
</style>
