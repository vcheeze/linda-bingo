<script>
  import Collapsible from 'spaper/components/Collapsible.svelte';
  import Button from 'spaper/components/Button.svelte';

  export let question;
  export let onClick;
</script>

<Collapsible label={question.id.toString()}>
  <h4>{question.label}</h4>
  {#if !!question.answer}
    <Button outline="success" on:click={onClick(question)}>
      See the answer!
    </Button>
  {/if}
</Collapsible>
