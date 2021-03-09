<script>
	export let name;
	import Greeting from './Greeting.svelte';
	import Math from './Math.svelte';
	let user = {loggedIn: false}
	function loginToggle() {
		user.loggedIn = !user.loggedIn;
	}
</script>
 
<main>
{#if user.loggedIn}
	<button on:click={loginToggle}>Log Out</button>
	<h2>This from the 'App' component</h2>
	<Math />
{:else}
	<button on:click={loginToggle}>Log In</button>
	<h1>Hello {name}!</h1>
	<Greeting firstName='Daniel' lastName='Hansen' />
{/if}
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
	h2 {
		color: blue;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>