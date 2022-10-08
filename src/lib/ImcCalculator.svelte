<script>
	const name = 'Nour-eddine';
	let poids = 80;
	let taille = 1.8;

	import Imc from './imc.svelte';
	import Form from './form.svelte';
</script>

<p>Bonjour {name}</p>

<Form bind:poids bind:taille />
<Imc {poids} {taille} />
