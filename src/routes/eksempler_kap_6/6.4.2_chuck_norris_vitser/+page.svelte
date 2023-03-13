<script>
// @ts-nocheck

	let joke
	const getJoke = async () => {
		const data = await fetch("https://api.chucknorris.io/jokes/random?category=dev")
		const json = await data.json()
		joke = json.value
	}
	getJoke()
</script>

<h1>Dagens vits</h1>

{#if joke}
	<p>{joke}</p>
{:else}
	<p>Laster inn vits...</p>
{/if}
