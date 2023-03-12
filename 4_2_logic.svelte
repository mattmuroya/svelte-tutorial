<script>
  import Thing from './4_2b_Thing.svelte';

  let things = [
    { id: 1, name: 'apple' },
    { id: 2, name: 'banana' },
    { id: 3, name: 'carrot' },
    { id: 4, name: 'doughnut' },
    { id: 5, name: 'egg' },
  ];

  function handleClick() {
    things = things.slice(1);
  }
</script>

<button on:click={handleClick}> Remove first thing </button>

<!-- By default, when value of `each` block is modified, items are added/removed at the bottom -->
<!-- Then svelte goes and updates any values that are changed -->
<!-- Can use unique "Key" identifiers to alter specific DOM nodes -->

{#each things as thing (thing.id)}
  <Thing name={thing.name} />
{/each}
