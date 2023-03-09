<script>
  import Nested from './1a_Nested.svelte';

  let name = 'world';
  let src = 'https://svelte.dev/tutorial/image.gif';
</script>

<h1>Hello {name.toUpperCase()}!</h1>

<img {src} alt="A man dances." />
<!-- {src} is shorthand for `src={src}` -->

<p>This is a paragraph.</p>
<Nested />

<style>
  p {
    color: purple;
    font-family: 'Comic Sans MS', cursive;
    font-size: 2em;
  }
</style>
