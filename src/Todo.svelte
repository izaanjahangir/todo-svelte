<script>
  export let todo, index, onDelete;

  import Button from "./Button.svelte";

  const handleDelete = () => {
    if (onDelete) {
      onDelete(index);
    }
  };
</script>

<div class="container">
  <p>{todo}</p>
  <Button onClick={handleDelete} color="red">Delete</Button>
</div>

<style>
  .container {
    background-color: #57606f;
    height: 40px;
    border-radius: 5px;
    padding: 5px 10px;
    display: flex;
    align-items: center;
    margin: 5px 0;
  }

  p {
    margin: 0;
    color: white;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1.1em;
    flex: 1;
  }
</style>
