<script>
	import { Motion as motion, AnimateSharedLayout } from 'motion-start'

	const spring = {
		type: 'spring',
		stiffness: 700,
		damping: 30
	}

	let active = $state(false)

	function toggleSwitch() {
		active = !active
	}
</script>

<AnimateSharedLayout>
	<button class="switch" data-active={active} onclick={toggleSwitch}>
		<motion.div layout class="handle" transition={spring} />
	</button>
</AnimateSharedLayout>

<p>This should animate on click</p>

<style>
	.switch {
		all: unset;
		width: 8rem;
		height: 3rem;
		background-color: gainsboro;
		display: flex;
		justify-content: flex-start;
		border-radius: 50px;
		padding: 0.5rem;
		cursor: pointer;
	}

	.switch[data-active='true'] {
		justify-content: flex-end;
	}

	:global(.handle) {
		width: 3rem;
		height: 3rem;
		background-color: white;
		border-radius: 40px;
	}
</style>
