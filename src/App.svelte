<script>
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

<style scoped>
	body{
		display: flex;
		justify-content: center;
		flex-direction: column;
		align-items: center;
		width: 100%;
	}
	.list{
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		background: slategray;
		border-radius: 10px;
		padding: 10px;
	}
	.todo{
		display: flex;
		flex-direction: row;
	}

</style>

<body>
	<h1 on:click={helloThere}>Hello, <span style="color: #063c81">{n}</span></h1>
	<div class="list">
		<input style="background: black; color: white;"bind:value={n}>
		<br>
		{#each todos as todo, index}
		<div class="todo">
			<input bind:value={todos[index]}>
			<button on:click={()=>removeTodo(index)}>X</button>
		</div>
		<br>
		{/each}
		<button on:click={addTodo}>Add Something</button>
	</div>
</body>