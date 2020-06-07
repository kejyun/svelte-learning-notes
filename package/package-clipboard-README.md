# 剪貼簿 ClipBoard

## App.svelte

```svelte
<script>
	import CopyClipBoard from './CopyClipBoard.svelte';

	let name = 'world';

	const copy = () => {
		const app = new CopyClipBoard({
			target: document.getElementById('clipboard'),
			props: { name },
		});
		app.$destroy();
	}
</script>

<input bind:value={name}>
<button on:click={copy}>copy</button>

<!-- 複製用  -->
<span id="clipboard"></span>
```

## CopyClipBoard.svelte

```svelte
<script>
	import { onMount } from 'svelte';

	export let name;

	let textarea;

	onMount(() => {
		textarea.select();
		document.execCommand('copy');
	});
</script>

<textarea bind:value={name} bind:this={textarea}></textarea>
```

## 參考資料
* [clipboard copy • REPL • Svelte](https://svelte.dev/repl/3194502389af4e22991f8bb0c61d65cf?version=3.16.5)
