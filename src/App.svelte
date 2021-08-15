<script>
	import { MyComponent, FileSelector, FileUploader } from './components';
	const name = 'World';
</script>

<div class="wrapper">
	<FileUploader />
</div>

<style>
	:global(body) {
		padding: 0 !important;
		margin: 0 !important;
		font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande',
			'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
	}
	:global(.FileSelector__button) {
		--button-bg: white;
	}
	/* .wrapper {
		width: 100vw;
		height: 100vh;
		display: flex;
		align-items: center;
	} */
</style>
