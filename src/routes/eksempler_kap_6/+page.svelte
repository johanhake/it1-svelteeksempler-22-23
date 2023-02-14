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
		],

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
