<script>
    // declare our props
    let num1 = 0;
    let num2 = 0;
    $: result = num1 * num2;  // reactively updating the result prop using the '$:' prefix
</script>

<h2>Math!</h2>
<!-- binding the input values to the props, then outputting the result prop -->
<input bind:value={num1}> x <input bind:value={num2}> = {result}