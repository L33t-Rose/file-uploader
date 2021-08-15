<script>
    /**@type {Function}*/
    export let handleFiles;
	function stopIt(e) {}
    function handleDrop(e){
        const {files} = e.dataTransfer;
        handleFiles(files)
    }
</script>

<div
	class="DropBox"
	on:dragenter|preventDefault|stopPropagation={stopIt}
	on:dragover|preventDefault|stopPropagation={stopIt}
    on:drop|preventDefault|stopPropagation={handleDrop}
>
	<slot/>  
</div>

<style>
    .DropBox{
        width:calc(100% - 4px);
        height:150px;
        background-color:#e6e6e6;
        display:flex;
        justify-content: center;
        align-items:center;
        border: 2px dashed;
    }
</style>
