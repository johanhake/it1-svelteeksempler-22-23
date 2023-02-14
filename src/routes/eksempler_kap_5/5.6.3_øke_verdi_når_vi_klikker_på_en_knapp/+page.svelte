<script>
	// Hvordan setter vi en grense slik at man IKKE kan klikke mer enn 42?
	let tall = 20
	const øk = () => {
		tall++
		if(tall>=42){
			tall = 42
		}
	}

</script>

<button on:click={øk}> + </button>
<p>
	Tallet er nå {tall}
</p>