<script>
	const name = 'Nour-eddine';
	let taille = 1.8;
	let poids = 80;

	let historique = [];

    function sauvegarderIMC(event) {
		historique = [...historique, event.detail];
	}

	import Imc from './imc.svelte';
	import Form from './form.svelte';
</script>

<p>Bonjour {name}</p>

<Form bind:poids bind:taille on:sauvegarder={sauvegarderIMC}/>
<h3>Evolution de l'IMC</h3>
<ul>
	{#each historique as item, index}
		<li>{index + 1}: {item.toFixed(2)}</li>
	{/each}
</ul>
<Imc {poids} {taille} />
