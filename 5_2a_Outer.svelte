<script>
  import Inner from './5_2b_Inner.svelte';
</script>

<!-- on:message with no callback "forwards" all message events from the Inner component upwards -->
<!-- on:click forwards the click from the other button -->
<Inner on:message on:click />
