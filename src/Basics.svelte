<!-- bascis, data binding, reactive values  -->
<script>
  let firstName = "Juan";
  let lastName = "Nicolai";
  let beltColor = "black";

  $: fullName = `${firstName} ${lastName}`;
  $: {
    console.log(beltColor);
    console.log(fullName);
  }

  const handleClick = () => {
    beltColor = "orange";
  };

  const handleInput = (e) => {
    beltColor = e.target.value;
  };
</script>

<p>{fullName} - {beltColor} belt</p>

<button on:click={handleClick}>Update belt color</button>
<!-- One way data binding -->
<input type="text" on:input={handleInput} value={beltColor} />

<input type="text" bind:value={firstName} />
<input type="text" bind:value={lastName} />
<!-- Two way data binding -->
<input type="text" bind:value={beltColor} />
