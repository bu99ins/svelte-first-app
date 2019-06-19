<script>
  import ContactCard from "./ContactCard.svelte";

  let name = "Max";
  let title = "";
  let image = "";
  let description = "";
  let done = false;

  function addContact() {
    done = true;
  }
</script>

<style>
  h1 {
    color: purple;
  }
</style>

<h1>Hello {name}!</h1>
<!-- <input type="text" value={name} on:input={nameInput} /> -->
<input type="text" bind:value={name} />
<input type="text" bind:value={title} />
<input type="text" bind:value={image} />
<textarea rows="3" bind:value={description} />

<button on:click={addContact}>Add Contact Card</button>

{#if done}
  <ContactCard
    userName={name}
    jobTitle={title}
    {description}
    userImage={image} />
{/if}
