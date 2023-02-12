<script>
	let a = 1
	let b = 1
	let c = 1
	let x = 1
	let y=0, a_T=0, b_T=0, x_E=0, y_E=0
	$:{
		y = a*x*x+b*x+c
		a_T = 2*a*x+b
		b_T = -a_T*x + y
		x_E = -b/(2*a)
		y_E = a*x_E*x_E+b*x_E+c
	}
</script>


<label>Skriv inn a: <input type="number" bind:value={a}></label>
<label>Skriv inn b: <input type="number" bind:value={b}></label>
<label>Skriv inn c: <input type="number" bind:value={c}></label>
<label>Skriv inn x: <input type="range" min="-10" max="10" bind:value={x}> {x} </label>
<p>
Funksjonen: f(x)={a}x<sup>2</sup>+{b}x+{c}
</p>
<p>
Deriverte: f'(x)={2*a}x+{b}
</p>
<p>
f({x})={y}
</p>
<p>
f'({x})={a_T}
</p>
<p>
	Likning til tangent: y={a_T}x+{b_T}
</p>
<p>
	Ekstremalpunkt: ({x_E}, {y_E})
</p>


<style>
	label{
		display: block;
	}
</style>