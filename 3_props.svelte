<script>
  import Nested from './3a_Nested.svelte';
  import Info from './3b_Info.svelte';

  const data = {
    name: 'Kintaro',
    breed: 'Golden Retriever',
    favoriteColor: 'purple',
    favoriteFood: 'peanut butter',
  };
</script>

<Nested answer={42} />
<Nested />

<!-- You can spread an object to pass all data as props. -->
<!-- Or, just pass them individually `name={data.name} breed={data.breed}...` etc -->
<Info {...data} />
