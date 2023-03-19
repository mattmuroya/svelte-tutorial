<script>
  let name = 'world';
</script>

<!-- the `bind` directive binds this input value to the name prop -->
<input bind:value={name} />

<!--
it's basically equivalent to:
<script>
  function updateName(e) {
		name = e.target.value;
	}
</script>
<input on:input={updateName} value={name}>
-->

<h1>Hello {name}!</h1>
