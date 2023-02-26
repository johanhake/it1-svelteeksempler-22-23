<script>
	// @ts-nocheck

	const data = fetch('https://kode-1.github.io/person.json');
	const person = data.json();

</script>

{#if person}
	<p>Navn: {person.navn}</p>
	<p>Alder: {person.alder}</p>
{:else}
	<p>Henter data...</p>
{/if}
