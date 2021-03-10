<script>
    // declare our props
    export let firstName;
    export let lastName; // the 'export' allows the props to be accessed outside of the component
</script>

<!-- Inputs for each name, reactively binding the value each input to each prop -->
<label for="firstName">First Name</label>
<input name="firstName" bind:value={firstName}>

<label for="lastName">Last Name</label>
<input name="lastName" bind:value={lastName}>

<!-- Outputting the prop in our h2 -->
<h2>This is an app for <span>{firstName} {lastName}</span></h2>

<style>
    /* This style is scoped to just this component */
    h2 {
        color: green;
    }
    span {
        border-bottom: 1px solid;
        min-width: 10em;
        display: inline-block;
    }
</style>