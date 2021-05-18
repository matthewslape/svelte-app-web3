<script>
	let name;
	let n = "Person?";
	let todos = [];

	function helloThere(name){
		n = name;
	}

	function removeTodo(index){
		todos = [...todos.slice(0, index), ...todos.slice(0, index + 1)];
	}

	function addTodo(){
		todos = [...todos, ''];
	}

</script>

<h3>please enter your name :)</h3>
<input bind:value={n}>
<h1 on:click={helloThere}>Hello, {n}!</h1>
{#each todos as todo, index}
<input bind:value={todos[index]}>
<button on:click={removeTodo}>X</button>
<br>
{/each}
<button on:click={addTodo}>Add Todo</button>