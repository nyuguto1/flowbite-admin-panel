<script lang="ts">
	import { Badge } from 'flowbite-svelte';
	import type { BadgeProps } from 'flowbite-svelte/Badge.svelte';

	export let state: keyof typeof states;
	export let dark: boolean = false;

	const states = {
		true: 'Complete',
		false: 'In Progress'
	};

	const colors: Record<string, BadgeProps['color']> = {
		true: 'green',
		false: 'purple'
	};
</script>

<Badge color={colors[state] ?? 'dark'} border={dark}>{states[state] ?? 'Unknown'}</Badge>
