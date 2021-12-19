<script>
    let name = "";
    let age = "";
    
    async function getAge() {
  fetch(' https://api.agify.io/?name=' + name)
	.then((response) => response.json())
	.then((data) => {
    name = data.name;
  	age = data.age; // Path for temperature
	});
}
</script>
<h1>Guess Age</h1>

<form on:submit|preventDefault={getAge}>
    <label for="name">name:</label>
    <input id="name" bind:value={name} type="text" />
    <button type="submit">Check</button>
</form>

<p>Age: {age}</p>
