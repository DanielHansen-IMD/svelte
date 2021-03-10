<script>
	export let name;
	// import our components
	import Greeting from './Greeting.svelte';
	import Math from './Math.svelte';
	// our user object, with a loggedIn value
	let user = {loggedIn: false}
	// a simple toggle function: if the user is logged in, then log them out
	function loginToggle() {
		user.loggedIn = !user.loggedIn;
	}
</script>
 
<main>
	//
{#if user.loggedIn} <!-- our Svelte conditional statement: if the user is logged in, show this stuff: -->
	<button on:click={loginToggle}>Log Out</button>
	<h2>This from the 'App' component</h2>
	<!-- display our Math component -->
	<Math />
{:else} <!-- otherwise (i.e. if the user is not logged in) show this other stuff: -->
	<button on:click={loginToggle}>Log In</button>
	<h1>Hello {name}!</h1>
	<!-- Display our Greeting component, with some default values for our component props -->
	<Greeting firstName='' lastName='' />
{/if}<!-- end the conditional statement -->
</main>

<style>
	/* This style is scoped to just this component */
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
	h2 {
		color: blue;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>