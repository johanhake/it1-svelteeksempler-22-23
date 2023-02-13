<script>
	const eksempler = [
		{nr:"5.2.2", navn: "Regnemesteren"},
		{nr:"5.2.3", navn: "Areal av vegg"},
		{nr:"5.2.4", navn: "Datatyper"},
		{nr:"5.2.5", navn: "Konkatenering"},
		{nr:"5.3", navn: "Bruk av Math"},
		{nr:"5", navn: "String metoder"},
		{nr:"5.3.1", navn: "Invitasjon"},
		{nr:"5.3.2", navn: "Omkretsen til en sirkel"},
		{nr:"5.3.3", navn: "Sette farge til en overskrift"},
		{nr:"5.3.8", navn: "Regnemaskin med reaktiv variabel"},
		{nr:"5.3.9", navn: "Areal av rektangel"},
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
	]


</script>

<h1>Ekesmpler fra kap 5</h1>
<ul>
	{#each eksempler as eks}
	<li>
		<a href="/eksempler_kap_5/{eks.nr}_{(eks.navn.toLowerCase().split(" ").join("_"))}">{eks.nr} {eks.navn}</a>
	</li>
	{/each}
</ul>

