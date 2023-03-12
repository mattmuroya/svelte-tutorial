<script>
  let user = { loggedIn: false };

  function toggle() {
    user.loggedIn = !user.loggedIn;
  }

  let x = 7;

  let cats = [
    { id: 'J---aiyznGQ', name: 'Keyboard Cat' },
    { id: 'z_AbfPXTKms', name: 'Maru' },
    { id: 'OUtn3pvWmpg', name: 'Henri The Existential Cat' },
  ];
</script>

{#if user.loggedIn}
  <button on:click={toggle}> Log out </button>
{:else}
  <button on:click={toggle}> Log in </button>
{/if}

{#if x > 10}
  <p>{x} is greater than 10</p>
{:else if x < 5}
  <p>{x} is less than 5</p>
{:else}
  <p>{x} is between 5 and 10</p>
{/if}

<h1>The Famous Cats of YouTube</h1>

<ul>
  {#each cats as cat, i}
    <li>
      <a
        target="_blank"
        href="https://www.youtube.com/watch?v={cat.id}"
        rel="noreferrer"
      >
        {i + 1}: {cat.name}
      </a>
    </li>
  {/each}
</ul>
