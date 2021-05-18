<script>
	let name;
	let n = "Human?";
	let todos = [];

	function helloThere(name){
		n = name;
	}

	function removeTodo(index){
		todos = [...todos.slice(0, index), ...todos.slice(index + 1)];
	}

	function addTodo(){
		todos = [...todos, ''];
	}

</script>

<h1 on:click={helloThere}>Hello, <span style="color: #063c81">{n}</span></h1>
<input style="background: black; color: white;"bind:value={n}>
<br>
{#each todos as todo, index}
<input bind:value={todos[index]}>
<button on:click={()=>removeTodo(index)}>X</button>
<br>
{/each}
<button on:click={addTodo}>Add Something</button>