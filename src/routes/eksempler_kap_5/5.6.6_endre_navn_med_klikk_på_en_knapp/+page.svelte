<script>
// @ts-nocheck

	let navn = "John Donne"
	const lagNyttNavn = (fornavn, etternavn) => {
		navn = fornavn + " " + etternavn

	}
</script>

<h1>
	Mitt navn er {navn}
</h1>
<!--
* Her kan vi IKKE bruke lagNyttNavnsom lytterfunksjon
* Vi kan HELLER IKKE bare kalle funksjonen når vi skal registrere den
* Vi må legge inn funksjonskallet i en annonym lytterfunksjon
-->
<button on:click={ ()=>{lagNyttNavn("Marie", "Curie")} }>
		Marie Curie
</button>
<button on:click={ ()=>{lagNyttNavn("James", "Bond")}}>
		James Bond
</button>
