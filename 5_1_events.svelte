<script>
  let m = { x: 0, y: 0 };

  function handleMousemove(e) {
    m.x = e.clientX;
    m.y = e.clientY;
  }
</script>

<div on:mousemove={handleMousemove}>
  The mouse position is ({m.x}, {m.y})
</div>

<!-- Event handlers can be declared inline instead of as a function in the <script> tag -->
<!-- Event handlers can have "modifiers" that alter behavior e.g. `once` to run that handler only once -->
<button on:click|once={() => alert('THIS IS YOUR ONLY WARNING MF')}>
  Click me
</button>

<!-- The full list of modifiers:

- preventDefault — calls event.preventDefault() before running the handler. Useful for client-side form handling, for example.

- stopPropagation — calls event.stopPropagation(), preventing the event reaching the next element

- passive — improves scrolling performance on touch/wheel events (Svelte will add it automatically where it's safe to do so)

- nonpassive — explicitly set passive: false

- capture — fires the handler during the capture phase instead of the bubbling phase (MDN docs)

- once — remove the handler after the first time it runs

- self — only trigger handler if event.target is the element itself

- trusted — only trigger handler if event.isTrusted is true. I.e. if the event is triggered by a user action.

You can chain modifiers together, e.g. on:click|once|capture={...}. -->
<style>
  div {
    width: 100%;
    height: 80%;
  }
</style>
