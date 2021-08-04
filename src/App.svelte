<script>
  import Card, { Content } from "@smui/card";
  import Textfield from "@smui/textfield";

  let todoText = "";
</script>

<div class="container">
  <div class="card-container">
    <Card style="height: 100%">
      <Content>
        <Textfield
          bind:value={todoText}
          class="shaped-outlined"
          variant="outlined"
          label="Label"
        />
      </Content>
    </Card>
  </div>
</div>

<style>
  .container {
    height: 100%;
    width: 100%;
    justify-content: center;
    align-items: center;
    display: flex;
  }

  .card-container {
    height: 90%;
    width: 90%;
  }
</style>
