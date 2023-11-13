<script lang="ts">
	import { createApp, setAppContext, App, Graphics, Container } from 'pixi-svelte';
	import { onMount } from 'svelte';

	const context = createApp();
	setAppContext(context);

	// Retrieving information from the Writable store
	let sizesData: any;
	const unsubscribe = context.canvasSizes.subscribe((value) => {
		sizesData = value;
	});

	// Accessing specific properties (width and height)
	const width = sizesData.width;
	const height = sizesData.height;
</script>

<App>
	<Container>
		<Graphics
			draw={(graphics) => {
				graphics.beginFill('#1099bb');
				graphics.drawRect(0, 0, 150, 150);
				graphics.endFill();
			}}
		/>
		<Container
			><Graphics
				draw={(graphics) => {
					graphics.lineStyle(2, '#000000', 1);
					graphics.beginFill('#1099bb');
					graphics.drawRect(1, 1, 50, 50);
					graphics.endFill();
				}}
			/></Container
		>
	</Container>
</App>
