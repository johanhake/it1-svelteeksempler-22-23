<script>
// @ts-nocheck

	const eksempler = [

	]


</script>

<h1>Ekesmpler fra kap 6</h1>
<h2>Kommer snart!</h2>
<ul>
	{#each eksempler as eks}
	<li>
		<a href="/eksempler_kap_6/{eks.nr}_{(eks.navn.toLowerCase().split(" ").join("_"))}">{eks.nr} {eks.navn}</a>
	</li>
	{/each}
</ul>

