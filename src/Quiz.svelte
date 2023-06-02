<script>

        // stuck on video number 9, would appear the quiz API is
        // not feeding through as expected, can't seem to get
        // the results etc to show in my debugger - next thing to sort

    let result;
    let correctAnswer = "b";
    let answers = ["a", "b", "c", "d"];
    let quiz = getQuiz();

    function pickAnswer(answer) {
        if (answer === correctAnswer) {
           return result = "Correct!"
        }
        result = "NA M8"
    }

    async function getQuiz() {
        const res = await fetch('https://opentdb.com/api.php?amount=10&category=12&difficulty=medium&type=multiple');
        const quiz = await res.json();
        debugger;
    }

</script>

<style>
    /* h4 {
        color: red;
    } */

</style>

<div>

    <button on:click={getQuiz}>Get questions</button>

    {#if result}
    <h4>{result}</h4>
    {:else}
        <h4>pick an answer</h4>
    {/if}

    <h3>{quiz.results[0].question}</h3>

    {#each answers as answer}
     <button on:click={() => pickAnswer(answer)}>
        Answer {answer.toUpperCase()}
    </button>
    {/each} 

</div>