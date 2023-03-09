<script>
  // declaring and updating variables is what drives reactivity
  let count = 0;

  // the `$:` syntax is valid (if unconventional) JS that Svelte interprets as
  // "re-run this code whenever any referenced values change"
  $: doubled = count * 2;

  // it can also be used to execute statements or blocks other than variable assignment
  $: console.log(`The count is ${count}`);
  $: if (count >= 10) {
    console.log('count is dangerously high!');
    count = 9;
  }

  function incrementCount() {
    count += 1;
  }

  let numbers = [1, 2, 3, 4];
  $: sum = numbers.reduce((a, b) => a + b);

  // reactivity is triggered by assignment, so mutating a value won't trigger updates
  // create a new assignment instead
  function addNumber() {
    numbers = [...numbers, numbers.length + 1];
    // you could also mutate the array `numbers.push()` and then assign it to itself `numbers = numbers`
    // or assign a property of the array/object e.g. `numbers[i] = numbers.length + 1`
    // note: indirect assignment will not trigger an update for the variable
  }
</script>

<h2>counter</h2>

<button on:click={incrementCount}>
  Clicked {count}
  {count === 1 ? 'time' : 'times'}
</button>

<p>{count} doubled is {doubled}</p>

<h2>number array</h2>

<p>{numbers.join(' + ')} = {sum}</p>

<button on:click={addNumber}> Add a number </button>
