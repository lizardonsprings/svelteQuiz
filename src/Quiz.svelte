<script>

    let result;
    let correctAnswer = "b";
    let answers = ["a", "b", "c", "d"]

    function pickAnswer(answer) {
        if (answer === correctAnswer) {
           return result = "Correct!"
        }
        result = "NA M8"
    }

</script>

<div>

    {#if result}
    <h4>{result}</h4>
    {:else}
        <h5>pick an answer</h5>
    {/if}
    {#each answers as answer}
     <button on:click={() => pickAnswer(answer)}>Answer {answer.toUpperCase()}</button>
    {/each}

</div>