<script>
// @ts-nocheck

	// Url mal (alle bildene starten med denne urlen)
	const url_mal = "https://johanhake.github.io/it2-kodeeksempler-21-22/Kapittel%206-12/bilder/"

	// Alle de syv ulike bildene
	const spiller_papir = url_mal + "spiller_papir.png"
	const spiller_stein = url_mal + "spiller_stein.png"
	const spiller_saks = url_mal + "spiller_saks.png"
	const maskin_ukjent = url_mal + "maskin_ukjent.png"
	let maskin_bilde = maskin_ukjent;
	let melding = "Gjør et valg!"
	let spiller_poeng = 0
	let maskin_poeng = 0
	let spille = false

	// Funksjon som kalles når en brukere skal starte et spill
	const startSpill = ()=>{
		spille = true
		spiller_poeng = 0
		maskin_poeng = 0
		melding = "Gjør et valg!"
	}

	// Funksjon som kalles når en brukere har gjort et valg
	const spillerValg = (valg) => {
		if (!spille){
			return
		}
		let maskin_valg = "stein";
		const tilfeldig = Math.trunc(Math.random()*3);
		if (tilfeldig === 1){
			maskin_valg = "saks";
		}else if (tilfeldig === 2){
			maskin_valg = "papir";
		}
		console.log(valg, maskin_valg)
		maskin_bilde = url_mal + "maskin_" + maskin_valg + ".png";

		// Sjekker for samme valg
		if (maskin_valg === valg){
				melding = "Uavgjort!"
		}else if(maskin_valg === "stein"){
			if (valg === "saks"){
				maskin_poeng += 1
				melding = "Maskinen fikk poeng"
			}else{
				spiller_poeng += 1
				melding = "Du fikk et poeng"
			}
		}else if (maskin_valg === "saks"){
			if (valg === "papir"){
				maskin_poeng += 1
				melding = "Maskinen fikk poeng"
			}else{
				spiller_poeng += 1
				melding = "Du fikk et poeng"
			}
		}else{
			if (valg === "stein"){
				maskin_poeng += 1
				melding = "Maskinen fikk poeng"
			}else{
				spiller_poeng += 1
				melding = "Du fikk et poeng"
			}
		}
		if (spiller_poeng === 3 || maskin_poeng === 3){
				spille = false
				if(spiller_poeng === 3){
					melding = "Du vant!"
				}else{
					melding = "Maskinen vant!"
				}
		}
	}

</script>
<main>
	<h2>
		Stein - Saks - Papir
		{#if !spille}
		<button on:click={startSpill}>
			Start spill
		</button>
		{/if}
	</h2>
	<h3>

		{melding}
		<br>Spiller poeng: {spiller_poeng} Maskin poeng: {maskin_poeng}
	</h3>
	<div id="bilder">
		<img src={spiller_stein} alt="stein" on:click={()=>{spillerValg("stein")}} on:keydown={()=>{}}>
		<img src={spiller_saks} alt="saks" on:click={()=>{spillerValg("saks")}} on:keydown={()=>{}}>
		<img src={spiller_papir} alt="papir" on:click={()=>{spillerValg("papir")}} on:keydown={()=>{}}>
	</div>
	<img src={maskin_bilde} alt="maskin valg">
</main>

<style>
	main{
		background-color: #ebf0f1;
		padding: 5px;
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
	#bilder+img{
		width: 100px;
	}
</style>