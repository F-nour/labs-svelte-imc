<script>
	import { storePoids, storeTaille } from './stores';

	let poids = 0;
	let taille = 0;

	function handleSubmit(event) {
		storePoids.set(poids);
		storeTaille.set(parseFloat(taille));
		dispatch('sauvegarder', (poids / taille ** 2).toFixed(2));
	}
</script>

<form on:submit|preventDefault={handleSubmit}>
	<label>
		Poids ({poids} kg) :
		<input
			name="poids"
			type="range"
			min="10"
			max="200"
			step="5"
			bind:value={poids}
		/>
	</label>

	<label>
		Taille ({taille} m) :
		<input
			name="taille"
			type="range"
			min="0.5"
			max="2.5"
			step="0.01"
			bind:value={taille}
		/>
	</label>

	<button type="submit">Sauvegarder</button>
</form>
