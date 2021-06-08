<script>
    import Todo from "./components/Todo.svelte";

    export let name;

    let todos = [
        { done: false, text: "blabla1", importance: 0 },
        { done: false, text: "blabla2", importance: 1 },
        { done: false, text: "blabla3", importance: 2 },
    ];

    function addTodo() {
        todos = todos.concat({ done: false, text: "", importance: 0 });
    }

    function removeTodo() {
        todos = todos.filter((todo) => !todo.done); // gibt nur das zurück, was true ergibt
    }
</script>

<main>
    <h1>Hello {name}!</h1>
    <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>

    {#each todos as todo}
        <Todo {todo} />
    {/each}

    <button on:click={addTodo}>Todo hinzufügen</button>
    <button on:click={removeTodo}>Leere Todos löschen</button>

</main>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
    }

    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }

    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }
</style>
