<script>
// @ts-nocheck

	let elever = [
	{
		fornavn: "Kristian",
		etternavn: "Bakken",
		kjønn: "M",
		klasse: "2STA"
	},
	{
		fornavn: "Thomas",
		etternavn: "Berg",
		kjønn: "M",
		klasse: "2STA"
	},
	{
		fornavn: "Cato",
		etternavn: "Havig",
		kjønn: "M",
		klasse: "2STA"
	},
	{
		fornavn: "Martin",
		etternavn: "Klausen",
		kjønn: "M",
		klasse: "2STA"
	},
	{
		fornavn: "Lukas",
		etternavn: "Sørbu",
		kjønn: "M",
		klasse: "2STA"
	},
	{
		fornavn: "William",
		etternavn: "Feren",
		kjønn: "M",
		klasse: "2STB"
	},
	{
		fornavn: "Sander",
		etternavn: "Notstad",
		kjønn: "M",
		klasse: "2STB"
	},
	{
		fornavn: "Tobias",
		etternavn: "Rian",
		kjønn: "M",
		klasse: "2STC"
	},
	{
		fornavn: "Abdallah",
		etternavn: "Minta",
		kjønn: "M",
		klasse: "2STD"
	},
	{
		fornavn: "Linus",
		etternavn: "Dragland",
		kjønn: "M",
		klasse: "2STE"
	},
	{
		fornavn: "Marthe",
		etternavn: "Asbjørnsen",
		kjønn: "F",
		klasse: "2STF"
	},
	{
		fornavn: "Aksel ",
		etternavn: "Banelind",
		kjønn: "M",
		klasse: "2STF"
	},
	{
		fornavn: "Herman",
		etternavn: "Ly",
		kjønn: "M",
		klasse: "2STF"
	},
	{
		fornavn: "Tristan",
		etternavn: "Mietle",
		kjønn: "M",
		klasse: "2STF"
	},
	{
		fornavn: "Gurveer",
		etternavn: "Singh",
		kjønn: "M",
		klasse: "2STF"
	},
	{
		fornavn: "Mats",
		etternavn: "Ekeberg",
		kjønn: "M",
		klasse: "3STA"
	},
	{
		fornavn: "Mathias",
		etternavn: "Hestnes",
		kjønn: "M",
		klasse: "3STA"
	},
	{
		fornavn: "Erik",
		etternavn: "Huse",
		kjønn: "M",
		klasse: "3STA"
	},
	{
		fornavn: "Thien",
		etternavn: "Nguyen",
		kjønn: "M",
		klasse: "3STA"
	},
	{
		fornavn: "Mathias",
		etternavn: "Schiøtz",
		kjønn: "M",
		klasse: "3STB"
	},
	{
		fornavn: "Andreas",
		etternavn: "Skancke",
		kjønn: "M",
		klasse: "3STB"
	},
	{
		fornavn: "Lukas",
		etternavn: "Veidahl",
		kjønn: "M",
		klasse: "3STB"
	},
	{
		fornavn: "Kamilla",
		etternavn: "Haukås",
		kjønn: "F",
		klasse: "3STD"
	},
	{
		fornavn: "Erika",
		etternavn: "Iden",
		kjønn: "F",
		klasse: "3STD"
	},
	{
		fornavn: "Hallvard",
		etternavn: "Langen",
		kjønn: "M",
		klasse: "3STD"
	},
	{
		fornavn: "Johan",
		etternavn: "Salim",
		kjønn: "M",
		klasse: "3STD"
	},
	{
		fornavn: "Emilie Sophie",
		etternavn: "Skjelstad",
		kjønn: "F",
		klasse: "3STD"
	},
	{
		fornavn: "Jonas",
		etternavn: "Sørli",
		kjønn: "M",
		klasse: "3STE"
	},
	{
		fornavn: "Jonathan",
		etternavn: "Gjefsen",
		kjønn: "M",
		klasse: "3STF"
	},
	{
		fornavn: "Nicolay",
		etternavn: "Schiøtz",
		kjønn: "M",
		klasse: "3STF"
	},
	{
		fornavn: "Elias",
		etternavn: "Westad",
		kjønn: "M",
		klasse: "3STF"
	}
]
	for (let elev of elever){
		elev.tilstede = true
	}

	// Reaktiv variabel som teller antall tilstede
	$: tilstede = elever.filter(a=>a.tilstede).length

	// Lytterfunksjon for å registrere tilstedeværelese for elev
	const byttTilstede = (elev)=>{
		elev.tilstede = !elev.tilstede
		elever = elever
	}

	// Lytterfunksjon for å sortere
	const sorter = (hva) =>{
		// Sortere hva etter stigende rekkefølge
		if (stigende[hva]){
			elever.sort((a,b)=>a[hva].localeCompare(b[hva]))
		}else{
			elever.sort((a,b)=>b[hva].localeCompare(a[hva]))
		}
		stigende[hva] = !stigende[hva]
		// Trigge oppdatering av tabellen
		elever = elever
	}

	// Objekt for å holde hvilken vei vi skal sortere
	let stigende = {
		fornavn: true,
		etternavn: true,
		klasse: true
	}

	</script>
	<h2>
		Tilstede: {tilstede} elever
	</h2>
	<table>
		<thead>
			<tr>
				<!-- Fikse reaktive sorterEtter -> retning -->
				<th on:click={()=>{sorter("fornavn")}}>Fornavn {#if stigende.fornavn}▼{:else}▲{/if}</th>
				<th on:click={()=>{sorter("etternavn")}}>Etternavn {#if stigende.etternavn}▼{:else}▲{/if}</th>
				<th on:click={()=>{sorter("klasse")}}>Klasse {#if stigende.klasse}▼{:else}▲{/if}</th>
			</tr>
		</thead>
		<tbody>
			{#each elever as elev}
				<tr on:click={()=>{byttTilstede(elev)}}>
					{#if elev.tilstede}
						<td class="tilstede">{elev.fornavn}</td>
						<td class="tilstede">{elev.etternavn}</td>
						<td class="klasse tilstede">{elev.klasse}</td>
					{:else}
						<td>{elev.fornavn}</td>
						<td>{elev.etternavn}</td>
						<td class="klasse">{elev.klasse}</td>
					{/if}
				</tr>
			{/each}
		</tbody>
	</table>
	<style>
		table{
			border-collapse: collapse;
			border: black 2px solid;
		}
		thead tr{
			background-color: lightgreen;
		}
		tbody tr:nth-child(even){
			background-color: lightgreen;
		}
		td, th {
			width: 120px;
			border: black 1px solid;
		}
		tr:hover{
			cursor: pointer;
		}

		.klasse{
			text-align: center;
		}

		.tilstede{
			font-weight:bold;
		}
</style>