<script>
  import ContactCard from "./ContactCard.svelte";

  let name = "Max";
  let title = "";
  let image = "";
  let description = "";
  let formstate = "empty";

  let createdContacts = [];

  function addContact() {
    if (
      name.trim().length == 0 ||
      title.trim().length == 0 ||
      image.trim().length == 0 ||
      description.trim().length == 0
    ) {
      formstate = "invalid";
      return;
    }

    createdContacts = [
      ...createdContacts,
      {
        name: name,
        jobTitle: title,
        imageUrl: image,
        desc: description
      }
    ];
    formstate = "done";
  }
</script>

<style>

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

{#if formstate === 'invalid'}
  <p>Invalid input</p>
{:else}
  <p>Please enter some data and hit the button</p>
{/if}

{#each createdContacts as contact, i}
  <h2># {i + 1}</h2>
  <ContactCard
    userName={contact.name}
    jobTitle={contact.jobTitle}
    description={contact.desc}
    userImage={contact.imageUrl} />
{:else}
  <p>Please start adding some contacts. We have found none!</p>
{/each}
