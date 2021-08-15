<script>
	/**@type {Function}*/
	export let handleFiles;
	let fileInput;
	function handleClick(e) {
		e.preventDefault();
		fileInput.click();
	}
	function handleChange() {
		const files = fileInput.files;
		handleFiles(files);
	}
</script>

<svelt:fragment>
	<button class="FileSelector__button" on:click={handleClick}
		>Select Files</button
	>
	<input
		bind:this={fileInput}
		multiple
		type="file"
		on:change={handleChange}
	/>
</svelt:fragment>

<style>
	:root {
		--button-bg: transparent;
		--button-txt-color: black;
	}
	input[type='file'] {
		display: none;
	}
	.FileSelector__button {
		all: unset;
		background-color: var(--button-bg);
		color: var(--button-txt-color);
		cursor: pointer;
		padding: 1em 1em;
	}
</style>
