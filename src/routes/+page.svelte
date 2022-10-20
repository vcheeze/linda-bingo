<script>
  import Modal from 'spaper/components/Modal/Modal.svelte';
  import Question from '$lib/components/Question.svelte';
  import questions from '$lib/questions';
  import hearts from '$lib/images/hearts.png';

  let showAnswer = false;
  let selectedQuestion = { id: 0, label: '', answer: ''};
</script>

<div class="bingo">
  <img class="bingo-img" src={hearts} alt="hearts" />
  <h1>Welcome to the Linda Bingo</h1>
  <div class="bingo-content">
    {#each questions as question}
      <Question question={question} onClick={(q) => { selectedQuestion = q; showAnswer = true }} />
      {/each}
    <Modal bind:active={showAnswer} title="Answer">
      <h3 class={selectedQuestion.id === 3 ? 'purple' : ''}>{selectedQuestion.answer}</h3>
    </Modal>
  </div>
</div>
<a href="https://www.flaticon.com/free-icons/heart" title="heart icons">Heart icons created by Freepik - Flaticon</a>

<style>
  .purple {
    color: purple;
  }

  .bingo {
    text-align: center;
    margin: 2rem 4rem;
  }

  .bingo-img {
    width: 4rem;
    border: none;
    margin: 0 auto;
  }

  h1 {
    margin: 0 0 2rem 0;
  }

  .bingo-content {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-column-gap: 20px;
    grid-row-gap: 10px;
  }
</style>
