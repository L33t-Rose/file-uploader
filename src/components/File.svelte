<script>
	/**@type {File}*/
	export let file;

	/**@type {Function}*/
	export let handleRemove;
</script>

<div class="File">
	<span>{file.name}</span>
	<button on:click={handleRemove}>Remove</button>
</div>

<style>
	.File {
		display: flex;
		justify-content: space-between;
		padding: 0.25em;
	}
	span {
		width: 100%;
		max-width: 20ch;
		overflow: hidden;
		white-space: nowrap;
		text-overflow: ellipsis;
	}
</style>
