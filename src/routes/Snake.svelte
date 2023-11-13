<script lang="ts">
	import { createApp, setAppContext, App, Graphics } from 'pixi-svelte';
	const context = createApp();
	setAppContext(context);
</script>

<App>
	<Graphics
		draw={(graphics) => {
			graphics.beginFill(0xde3249);
			graphics.drawRect(0, 0, 150, 150);
			graphics.endFill();
		}}
	/>
</App>
