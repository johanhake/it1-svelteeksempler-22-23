<script>
	const eksempler = [
		[
			{nr:"6.0.1", navn: "For-løkke Summer"},
			{nr:"6.0.2", navn: "For-løkke Telle antall seksere"},
			{nr:"6.0.3", navn: "For-løkke Gå igjennom en array med verdier"},
			{nr:"6.0.4", navn: "Each-løkke Vise en liste med verdier"},
		],[
			{nr:"6.1.1", navn: "Skurker og tall"},
			{nr:"6.1.2", navn: "Filmer"},
			{nr:"6.1.3", navn: "Filmplakater"},
			{nr:"6.1.4", navn: "Sharknado-filmer"},
			{nr:"6.1.5", navn: "Legge til array fra input-felt"},
			{nr:"6.1.6", navn: "Legge til array fra checkboxer"},
			{nr:"6.1.8", navn: "Sortere en array med tekst"},
			{nr:"6.1.9", navn: "Sortere en array med tall"},
		],[
			{nr:"6.2.1", navn: "Endre verdi til objekt"},
			{nr:"6.2.2", navn: "Objekter i lister"},
			{nr:"6.2.3", navn: "Filtrere liste med filmer etter genre"},
			{nr:"6.2.4", navn: "Legge til skurker"},
		],[
			{nr:"6.3.2", navn: "Lese inn data fra en JSON-fil"},
			{nr:"6.3.4", navn: "Vise frem en liste med kjente gitarer"},
		],[
			{nr:"6.4.2", navn: "Chuck Norris vitser"},
			{nr:"6.4.3", navn: "Sminkevarer"},
			{nr:"6.4.5", navn: "Emojisøk"},
		],[
			{nr:"6.5.1", navn: "Lagre data"},
			{nr:"6.5.2", navn: "Hente frem data"},
		]
	]

	const oppgaver = [
		{nr:"6.03", navn: "Datamengde"},
		{nr:"6.04", navn: "Telletall"},
		{nr:"6.05", navn: "Tegne en linje"},
		{nr:"6.06", navn: "Registrere stemmer"},
		{nr:"6.07", navn: "Pinnkoder"},
		{nr:"6.10", navn: "Sortere meny"},
		{nr:"6.12", navn: "Fotballtabell"},
		{nr:"6.13", navn: "Registrere fravær elever checkbox"},
		{nr:"6.13", navn: "Registrere fravær elever"},
		{nr:"6.13", navn: "Registrere fravær elever json"},
		{nr:"6.13", navn: "Registrere fravær elever full"},
		{nr:"6.14", navn: "Landinformasjon"},
		{nr:"6.15", navn: "Sprinttider"},
		{nr:"6.16", navn: "Alfabetet"},
		{nr:"6.17", navn: "Brukernavn"},
		{nr:"6.18", navn: "Landinfo"},
		{nr:"6.23", navn: "MovieDB"},
	]

</script>

<h1>Eksempler fra kap 6</h1>

<div class="eksempler">
{#each eksempler as undereksempler, under_indeks}
	<div>
		{#each undereksempler as eks, eks_indeks}
			{#if eks_indeks == 0}
				<h3>Eksempler fra 6.{under_indeks}</h3>
			{/if}
			<a href="/eksempler_kap_6/{eks.nr}_{(eks.navn.toLowerCase().split(" ").join("_"))}">{eks.nr} {eks.navn}</a>
		{/each}
	</div>
	{/each}
</div>
<h1>Oppgaver fra kap 6</h1>
<div class="oppgaver">
{#each oppgaver as oppgave}
	<a href="/eksempler_kap_6/Oppgave_{oppgave.nr}_{(oppgave.navn.toLowerCase().split(" ").join("_"))}">{oppgave.nr} {oppgave.navn}</a>
{/each}
</div>

<style>
	.eksempler{
		display: flex;
		gap: 10px;
	}
	.eksempler > div, .oppgaver{
		flex: 0 1 250px;
		display: flex;
		flex-direction: column;
	}
	.eksempler > div > h3{
		text-align: center;
	}
	.eksempler > div a, .oppgaver a{
		text-decoration: none;
		padding: 10px;
	}
	.eksempler > div a:hover, .oppgaver a:hover{
		background-color: antiquewhite;
	}
</style>
