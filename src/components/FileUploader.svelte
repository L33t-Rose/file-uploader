<script>
	import DropBox from './DropBox.svelte';
	import File from './File.svelte';
	import FileSelector from './FileSelector.svelte';
	let files = [];
	let hasFiles = files.length > 0;
	$: {
		console.log(files);
		hasFiles = files.length > 0;
	}
	function handleFiles(newFiles) {
		files = [...Array.from(newFiles), ...files];
	}

	function handleRemove(i) {
		const newFiles = files.slice();
		newFiles.splice(i, 1);
		files = newFiles;
	}
</script>

<div class="FileUploader">
	<DropBox {handleFiles}>
		<FileSelector {handleFiles} />
	</DropBox>
	{#if hasFiles}
		<div class="FileUploader__fileView">
			{#each files as file, i (file.name + file.size)}
				<File
					{file}
					handleRemove={() => {
						handleRemove(i);
					}}
				/>
			{/each}
		</div>
	{/if}
</div>

<style>
	.FileUploader__fileView {
		min-height: 29px;
		max-height: 87px;
		overflow-y: scroll;
	}
</style>
