<script>
  import ContactCard from "./ContactCard.svelte";

  let name = "Max";
  let title = "";
  let image = "";
  let description = "";
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
<input type="text" bind:value={title} />
<input type="text" bind:value={image} />
<textarea rows="3" bind:value={description} />

<ContactCard userName={name} jobTitle={title} {description} userImage={image} />
