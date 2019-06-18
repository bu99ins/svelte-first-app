<script>
  export let userName;
  export let jobTitle;
  export let userImage;
  export let description;
</script>

<style>

</style>

<div>
  <header>
    <div>
      <img src={userImage} alt="" />
    </div>
    <h1>{userName}</h1>
    <h2>{jobTitle}</h2>
  </header>
  <div>
    <p>{description}</p>
  </div>
</div>
