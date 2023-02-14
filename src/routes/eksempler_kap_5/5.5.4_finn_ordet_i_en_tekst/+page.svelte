<script>
	let tekst = "Lille Petter Edderkopp. Han klatret på min hatt. Så begynte det å regne og Petter ned han datt. Så kom solen og skinte på min hatt. Da ble det liv i Petterkopp som klatret på min hatt"

	$: visTekst = tekst.replace(søkeord, "<b>" + søkeord + "</b>")
	let søkeord = "mai"

	$: ordetErFunnet = tekst.includes(søkeord)
	   // Vis teksten og uthev funnet søkeord med hjelp av tekst.replace(søkeord, ...)
	   // Bruk {@html tekstHTML} for å rendrere html i teksten
   </script>

   <input bind:value={søkeord}>
   {#if ordetErFunnet}
	  <p>Søkeordet er funnet i teksten</p>
   {:else}
	  <p>Søkeordet er <b>ikke</b> funnet i teksten</p>
   {/if}
   {@html visTekst}