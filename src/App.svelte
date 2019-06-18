<script>
  import ContactCard from "./ContactCard.svelte";

  let name = "Max";
  let age = 30;

  function incrementAge() {
    age += 1;
  }
</script>

<style>
  h1 {
    color: purple;
  }
</style>

<h1>Hello {name}, my age is {age}!</h1>
<button on:click={incrementAge}>Change Age</button>
<!-- <input type="text" value={name} on:input={nameInput} /> -->
<input type="text" bind:value={name} />

<ContactCard userName={name} />
