<script>
  import Outer from './5_2a_Outer.svelte';

  function handleMessage(e) {
    console.log(e.detail.text);
  }

  function handleClick() {
    console.log('Button Clicked');
  }
</script>

<!-- Components can also dispatch events with an event dispatcher -->
<!-- Parent component listens for `message` event dispatched by `Inner` component -->
<!-- In order to bubble up deeply nested (Inner) event dispatches, you need to forward the event through Outer component -->
<!-- You can also forward DOM events -->

<Outer on:click={handleClick} on:message={handleMessage} />
