<script>
	let name;
	let message;
	let todos = [];

	function helloThere(name){
		message = `Hello, ${name}!`;
	}

	function removeTodo(index){
		todos = [...todos.slice(0, index), ...todos.slice(0, index + 1)];
	}

	function addTodo(){
		todos = [...todos, ''];
	}

</script>

<h3>please enter your name :)</h3>
<input bind:value={name}>
<h1 on:blur={helloThere}>{message}</h1>
{#each todos as todo, index}
<input bind:value={todos[index]}>
<button on:click={removeTodo}>X</button>
<br>
{/each}
<button on:click={addTodo}>Add Todo</button>