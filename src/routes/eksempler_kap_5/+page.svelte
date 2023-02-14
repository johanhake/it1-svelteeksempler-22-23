<script>
	const eksempler = [
		[
			{nr:"5.2.2", navn: "Regnemesteren"},
			{nr:"5.2.3", navn: "Areal av vegg"},
			{nr:"5.2.4", navn: "Datatyper"},
			{nr:"5.2.5", navn: "Konkatenering"},
		],[
			{nr:"5.3", navn: "Bruk av Math"},
			{nr:"5", navn: "String metoder"},
			{nr:"5.3.1", navn: "Invitasjon"},
			{nr:"5.3.2", navn: "Omkretsen til en sirkel"},
			{nr:"5.3.3", navn: "Sette farge til en overskrift"},
			{nr:"5.3.8", navn: "Regnemaskin med reaktiv variabel"},
			{nr:"5.3.9", navn: "Areal av rektangel"},
		],[
			{nr:"5x", navn: "Andregrads-funksjon"},
			{nr:"5.4.1", navn: "Sant usant"},
			{nr:"5.4.2", navn: "If-setning"},
			{nr:"5.4.3", navn: "Ruter bilett"},
			{nr:"5.4.4", navn: "Rik og eller berømt"},
			{nr:"5.4.5", navn: "Gaming"},
			{nr:"5.4.6", navn: "Ruter bilett svelte"},
			{nr:"5.4.6.5", navn: "Ruter bilett svelte med spørsmåls-operator"},
			{nr:"5.4.7", navn: "Sammenligne tekster"},
			{nr:"5.4.8", navn: "Rik og eller berømt svelte"},
		],[
			{nr:"5.5.1", navn: "Telle antall tegn og ord"},
			{nr:"5.5.2", navn: "Grense for antall tegn tilatt"},
			{nr:"5.5.3", navn: "Sjekk svar fra Quiz"},
			{nr:"5.5.4", navn: "Finn ordet i en tekst"},
		],[
			{nr:"5.6.1", navn: "Bytt ordet med en funksjon"},
			{nr:"5.6.3", navn: "Øke verdi når vi klikker på en knapp"},
			{nr:"5.6.4", navn: "Snurre en tekst rundt når vi klikker på en knapp"},
			{nr:"5.6.5", navn: "Funksjon med to parameterer"},
			{nr:"5.6.6", navn: "Endre navn med klikk på en knapp"},
			{nr:"5x", navn: "Stein Saks Papir start"},
			{nr:"5x", navn: "Stein Saks Papir løsning"},
			{nr:"5x", navn: "Andregradslikning"},
		]
	]

</script>

<h1>Eksempler fra kap 5</h1>

<div class="eksempler">
{#each eksempler as undereksempler, under_indeks}
	<div>
		{#each undereksempler as eks, eks_indeks}
			{#if eks_indeks == 0}
				<h3>Eksempler fra 5.{under_indeks+2}</h3>
			{/if}
			<a href="/eksempler_kap_5/{eks.nr}_{(eks.navn.toLowerCase().split(" ").join("_"))}">{eks.nr} {eks.navn}</a>
		{/each}
	</div>
	{/each}
</div>

<style>
	.eksempler{
		display: flex;
		gap: 10px;
	}
	.eksempler > div{
		flex: 0 1 250px;
		display: flex;
		flex-direction: column;
	}
	.eksempler > div > h3{
		text-align: center;
	}
	.eksempler > div a{
		text-decoration: none;
		padding: 10px;
	}
	.eksempler > div a:hover{
		background-color: antiquewhite;
	}
</style>
