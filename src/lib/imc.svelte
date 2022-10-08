<script>
	import { storePoids, storeTaille } from './stores';
	$: imc = ($storePoids / $storeTaille ** 2).toFixed(2);
	$: thin = imc < 18;
	$: bold = imc > 25;
</script>

<p class:thin class:bold>
	Votre IMC ({$storePoids}/{$storeTaille}<sup>2</sup>) est de {imc}
</p>
{#if imc < 18}
	<p class="souspoids">Vous êtes maigre</p>
{:else if imc > 25}
	<p class="surpoids">Vous êtes en surpoids</p>
{:else}
	<p class="normal">Vous êtes svelte !</p>
{/if}

<style>
	.normal {
		color: green;
	}

	.surpoids {
		color: red;
	}

	.souspoids {
		color: orange;
	}

	.thin {
		font-weight: 200;
		font-size: 0.875rem;
	}
	.bold {
		font-weight: 600;
		font-size: 1.125rem;
	}
</style>
