<script lang="ts">
  import { superForm } from 'sveltekit-superforms';
  import SuperDebug from 'sveltekit-superforms';

  export let data;

  // Client API:
  const { form } = superForm(data.form);
</script>

<form method="POST">
  <label for="name">Name</label>
  <input class="input" type="text" name="name" bind:value={$form.name} />
  

  <label for="email">E-mail</label>
  <input class="input"  type="email" name="email" bind:value={$form.email} />

  <div>
    <button type="button" class="btn variant-filled">Submit</button>
  </div>
</form>

<SuperDebug data={$form} />