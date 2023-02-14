<script>
// @ts-nocheck

	// Url mal (alle bildene starten med denne urlen)
	const url_mal = "https://johanhake.github.io/it2-kodeeksempler-21-22/Kapittel%206-12/bilder/"

	// Alle de syv ulike bildene
	const spiller_papir = url_mal + "spiller_papir.png"
	const spiller_stein = url_mal + "spiller_stein.png"
	const spiller_saks = url_mal + "spiller_saks.png"
	const maskin_papir = url_mal + "maskin_papir.png"
	const maskin_stein = url_mal + "maskin_stein.png"
	const maskin_saks = url_mal + "maskin_saks.png"
	const maskin_ukjent = url_mal + "maskin_ukjent.png"
	let maskin_valg = maskin_ukjent;
	let melding = ""
	let spiller = true;

	// Funksjon som kalles når en brukere har gjort et valg
	const spillerValg = (valg) => {
		if(!spiller){
			return
		}
		console.log(valg)
		const tilfeldig = Math.trunc(Math.random()*3);
		if (tilfeldig === 0){
			maskin_valg = maskin_stein;
		}else if (tilfeldig === 1){
			maskin_valg = maskin_saks;
		}else{
			maskin_valg = maskin_papir;
		}

		// Hvilken logikk må det være her for at koden skal funke?
	}

</script>
<main>
	<h2>
		Stein - Saks - Papir
	</h2>
	<div id="bilder">
		<img src={spiller_stein} alt="stein" on:click={()=>{spillerValg("stein")}} on:keydown={()=>{}}>
		<img src={spiller_saks} alt="saks">
		<img src={spiller_papir} alt="papir">
	</div>
	<img src={maskin_valg} alt="maskin valg">
	<h2>
		{melding}
	</h2>
</main>

<style>
	main{
		background-color: #ebf0f1;
	}
	#bilder{
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		width: 100%;
	}
	#bilder img{
		width: 100%;
		transition: 0.125s;
	}
	#bilder img:hover{
		transform: scale(1.05)
	}
</style>