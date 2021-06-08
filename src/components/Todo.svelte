<script>
    import Importance from "./Importance.svelte";

    export let todo;
</script>

<div>
    <input type="checkbox" bind:checked={todo.done} />
    <input type="text" bind:value={todo.text} placeholder="Todotext" disabled={todo.done} />
    <Importance bind:importance={todo.importance} done={todo.done} />
</div>
<pre>{JSON.stringify(todo)}</pre>
