<script>
	let name = 'Matthew';
	let todos = [];

	function removeTodo(){
		todos = [...todos.slice(0, index), ...todos.slice(0, index + 1)];
	}

	function addTodo(){
		todos = [...todos, ''];
	}

</script>

<h1>Hello {name}!</h1>
{#each todos as todo, index}
<input bind:value={todos[index]}>
<button on:click={removeTodo}>X</button>
<br>
{/each}
<button on:click={addTodo}>Add Todo</button>