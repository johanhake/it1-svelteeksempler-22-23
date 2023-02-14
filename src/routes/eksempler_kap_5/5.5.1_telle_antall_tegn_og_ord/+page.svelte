<script>
	let tekst = ""
	// Hvordan kan vi fikse slik at antall ord blir telt?
</script>

<textarea bind:value={tekst}></textarea>
<p>
	Du har nå skrevet {tekst.length} tegn og <b>{tekst.split(" ").length}</b> ord
</p>

<style>
	textarea {
		width: 300px;
		height: 250px;
	}
</style>
