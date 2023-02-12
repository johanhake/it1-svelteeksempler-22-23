<script>
	let rik = true
	let berømt = true
	let melding = "Du kommer ikke inn 😢"
	// Test med både || og &&
	if(rik && berømt) {
		melding = "Du kommer inn 🥳"
	}

</script>

<h1>{melding}</h1>