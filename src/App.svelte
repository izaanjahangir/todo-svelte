<script>
  import Card, { Content } from "@smui/card";
  import Textfield from "@smui/textfield";
  import Button, { Label } from "@smui/button";

  import Todo from "./Todo.svelte";

  let todoText = "";
  let todos = [];

  const addTodo = () => {
    todos = [todoText, ...todos];
    todoText = "";
  };

  const handleTodoDelete = (index) => {
    todos.splice(index, 1);
    todos = [...todos];
  };
</script>

<div class="container">
  <div class="card-container">
    <Card style="height: 100%">
      <Content style="height: 100%; display: flex; flex-direction: column;">
        <Textfield
          bind:value={todoText}
          class="shaped-outlined"
          style="width: 100%"
          variant="outlined"
          label="Enter your todo..."
        />
        <div class="button-container">
          <Button
            disabled={!todoText}
            color="primary"
            on:click={addTodo}
            variant="outlined"
          >
            <Label>Add Todo</Label>
          </Button>
        </div>

        <div class="todo-container">
          {#each todos as todo, index}
            <Todo onDelete={handleTodoDelete} {todo} {index} />
          {/each}
        </div>
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
    background-color: #2f3542;
  }

  .card-container {
    height: 90%;
    width: 90%;
    max-width: 550px;
    overflow-y: hidden;
  }

  .button-container {
    margin-top: 10px;
    display: flex;
    justify-content: flex-end;
  }

  .todo-container {
    overflow-y: auto;
    flex: 1;
    margin: 10px 0;
    padding: 0 5px;
  }
</style>
