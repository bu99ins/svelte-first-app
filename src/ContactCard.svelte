<script>
  export let userName;
  export let jobTitle;
  export let userImage;
  export let description;

  const initalName = userName;
</script>

<style>
  .thumb-placeholder {
    background: #ccc;
  }
</style>

<div>
  <header>
    <div class="thumb" class:thumb-placeholder={!userImage}>
      <img src={userImage} alt="" />
    </div>
    <h1>{userName} / {initalName}</h1>
    <h2>{jobTitle}</h2>
  </header>
  <div>
    <p>{description}</p>
  </div>
</div>
