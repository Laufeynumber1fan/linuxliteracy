# Chapter 1

```bash,ocirun,editable
ls -l
ls ..
```
hi
<script type="module"> 
	import @wasmer/wasi from 'https://cdn.jsdelivr.net/npm/@wasmer/wasi@1.2.2/+esm'
	const response = await fetch('../bash.wasm');
	const wasmBinary = await response.arrayBuffer();
	
	const wasi = new WASI({
		args: ['bash', '-c', 'echo HELLO'],
		env: {}
	});

	await wasi.instantiate(wasmBinary, {});
	wasi.start(instance);
</script>
