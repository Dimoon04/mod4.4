<script>
	import {createEventDispatcher} from 'svelte'
	const dispatch = createEventDispatcher();

	let num1 = 0;
	let num2 = 0;
	let action = '+';
	let result = 0;

	function calculate(){
		switch(action){
			case '+':
				result = num1 + num2;
				break;
			case '-':
				result = num1 - num2;
				break;
			case '*':
				result = num1 * num2;
				break;
			case '/':
				result = num1 / num2;
				break;
			
		}
		dispatch('calculation', {result});
	}
</script>
<svelte:head>
	<title>About</title>
	<meta name="description" content="About this app" />
</svelte:head>

<div class="text-column">
	<h1>Простой калькулятор</h1>
		<input type="number" name="" placeholder="Ввелите первое число" bind:value={num1}>
		<select bind:value={action}>
			<option value="+">+</option>
			<option value="-">-</option>
			<option value="*">*</option>
			<option value="/">/</option>
		</select>
		<input type="number" name="" placeholder="Ввелите второе число" bind:value={num2}>
		<button on:click={calculate}>Посчитать</button>
		{#if result !== 0}
			<p>Результат: {result}</p>
		{/if}
	<!-- <script>
		import {createEventDispacher} from 'svelte'
		const dispatch = createEventDispacher();
	
		let num1 = 0;
		let num2 = 0;
		let action = '+';
		let result = 0;
	
		function calculate(){
			switch(action){
				case '+':
					result = num1 + num2;
					break;
				case '-':
					result = num1 - num2;
					break;
				case '*':
					result = num1 * num2;
					break;
				case '/':
					result = num1 / num2;
					break;
				
			}
			dispatch('calculation', {result});
		}
	</script>
	<main>
		<h1>Простой калькулятор</h1>
		<input type="number" name="" placeholder="Ввелите первое число" bind:value={num1}>
		<select bind:value={action}>
			<option value="+">+</option>
			<option value="-">-</option>
			<option value="*">*</option>
			<option value="/">/</option>
		</select>
		<input type="number" name="" placeholder="Ввелите второе число" bind:value={num2}>
		<button on:click={calculate}>Посчитать</button>
		{#if result !== 0}
			<p>Результат: {result}</p>
		{/if}
	</main> -->
</div>
