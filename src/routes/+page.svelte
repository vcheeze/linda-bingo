<script>
  import Modal from 'spaper/components/Modal/Modal.svelte';
  import Question from '$lib/components/Question.svelte';
  import questions from '$lib/questions';

  let showAnswer = false;
  let selectedQuestion = { id: 0, label: '', answer: ''};
</script>

<div class="bingo">
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

<style>
  .purple {
    color: purple;
  }

  .bingo {
    text-align: center;
    margin: 40px 20px;
  }

  .bingo-content {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-column-gap: 20px;
    grid-row-gap: 10px;
  }
</style>
