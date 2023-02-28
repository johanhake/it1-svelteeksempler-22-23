<script>
	import varer from "./nettbutikk.json";

	// Legger inn antall i hvert vare-objekt
	for (let vare of varer){
		vare.antall = 0
	}

	// Handlekurv
	let handlekurv = [];

	// Variabel for total pris
	// Lag reaktiv kode som beregner totalprisen til det som er i handlekurven
	$: totalPris = 0;

	// Variabel for visning av pris
	let visMaksPris = 2600;

	// Viser handlekurven
	let viserKurv = false;

	// Variabel for hvilket plagg som skal vises
	let visPlagg = "alle";

	// Viser handlekurven
	const visKurv = () => {
		console.log("vis kurv");
		viserKurv = !viserKurv;
	};

	// Tømmer handlekurven
	const tomKurv = () => {
		console.log("tøm handlekurv");
	};

	// Legger i handlekurv
	const leggIHandlekurv = (vare) => {
		console.log("Legger", vare.navn, "i handlekurv")
	}

</script>

<link
	rel="stylesheet"
	href="https://cdnjs.cloudflare.com/ajax/libs/foundation/6.6.1/css/foundation.min.css"
/>
<header>
	<nav>
		<select bind:value={visPlagg}>
			<option value="alle">Vis alle</option>
			<option value="skjorte">Vis Skjorter</option>
			<option value="bukse">Vis Bukser</option>
		</select>
		<button class="button success {viserKurv ? 'filter' : ''}" on:click={visKurv}>Handlekurv</button>
		<button class="button warning" on:click={tomKurv}>Tøm handlekurv</button>
		<label>
			<input type="range" min="100" max="2600" step="100" bind:value={visMaksPris}>
			{visMaksPris} kr
		</label>
	</nav>
</header>
{#if viserKurv}
	<sidebar id="txtHandlekurv">
		<h3>Handlekurv</h3>
		<!-- Går igjennom alle varene i handlekurven -->
		{#each handlekurv as kurv}
			{kurv.navn}
		{/each}

		<article><b>Total pris:</b></article>
		<article><b>{totalPris} kr</b></article>
	</sidebar>
{:else}
	<main>
		<!-- Går igjennom alle varene i listen varer-->
		{#each varer as vare}
			<article>
				<img src="/butikkbilder/{vare.bilde}" alt="" />
				<h6>{vare.type} {vare.navn} <i>{vare.pris} kr</i></h6>
				<input type="number" bind:value={vare.antall} min="0" />
				<button class="button" on:click={()=>{leggIHandlekurv(vare)}}>Legg i Handlekurv</button>
			</article>
		{/each}
	</main>
{/if}

<style>

	.filter{
		opacity: 0.5;
	}

	header nav {
		display: grid;
		grid-template-columns: repeat(5, 1fr);
	}

	main {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		grid-gap: 10px;
	}

	article img {
		width: 100%;
	}

	@media (max-width: 1100px) {
		main {
			grid-template-columns: 1fr 1fr 1fr;
		}
	}

	@media (max-width: 900px) {
		main {
			grid-template-columns: 1fr 1fr;
		}
	}

	@media (max-width: 700px) {
		main {
			grid-template-columns: 1fr;
		}
		header nav {
			grid-template-columns: 1fr;
		}

		header nav button {
			margin: 0;
		}
	}

	/* Vil bare brukes hvis handlekurv er med */
	#txtHandlekurv {
		display: grid;
		grid-template-columns: 3fr 1fr;
		width: 400px;
	}

	#txtHandlekurv h3 {
		grid-column: span 2;
	}
</style>
