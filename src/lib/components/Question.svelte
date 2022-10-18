<script>
  import Collapsible from 'spaper/components/Collapsible.svelte';
  import Button from 'spaper/components/Button.svelte';

  export let question;
  export let onClick;
</script>

<Collapsible label={question.id.toString()}>
  <p>{question.label}</p>
  {#if !!question.answer}
    <Button outline="success" on:click={onClick(question)}>
      See the answer!
    </Button>
  {/if}
</Collapsible>
