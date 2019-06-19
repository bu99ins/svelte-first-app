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

<div class="form-control">
  <label for="userName">User Name</label>
  <!-- <input type="text" value={name} on:input={nameInput} /> -->
  <input type="text" bind:value={name} id="userName" />
</div>

<div class="form-control">
  <label for="jobTitle">Job Title</label>
  <input type="text" bind:value={title} id="jobTitle" />
</div>

<div class="form-control">
  <label for="imageUrl">Image URL</label>
  <input type="text" bind:value={image} id="imageURl" />
</div>

<div class="form-control">
  <label for="description">Description</label>
  <textarea rows="3" bind:value={description} id="description" />
</div>

<button on:click={addContact}>Add Contact Card</button>

{#if done}
  <ContactCard
    userName={name}
    jobTitle={title}
    {description}
    userImage={image} />
{/if}
