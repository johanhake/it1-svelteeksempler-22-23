<script>
	let fasit = "Gro Harlem Brundtland"
	let fasitSmåBokstaver = fasit.toLowerCase()

	let svar = ""
	$: svarSmåBokstaver = svar.toLowerCase()

</script>

<h1>Hvem var Norges første kvinnelig statsminister?</h1>
<input bind:value={svar}>

{#if svarSmåBokstaver === fasitSmåBokstaver}
	<p>Det er helt riktig!</p>
{/if}
