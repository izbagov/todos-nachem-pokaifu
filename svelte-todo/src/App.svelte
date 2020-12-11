<script>
	let todos = [
		{
			id: +new Date(),
			value: "Make food for live life",
			completed: false,
		},
	];

	$: console.log(todos);

	import Search from "./components/Search.svelte";
	import Todo from "./components/Todo.svelte";
</script>

<style>
	main {
		max-width: 460px;
		margin: 0 auto;
	}

	h1 {
		font-size: 48px;
		font-weight: normal;
		text-transform: uppercase;
		color: #f44336;
		margin: 20px 0;
	}
</style>

<main>
	<h1>My todos</h1>
	<Search bind:todos />
	{#each todos as todo}
		<Todo bind:todo bind:todos />
	{/each}
</main>
