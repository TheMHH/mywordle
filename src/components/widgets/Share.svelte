<script lang="ts">
	import type Toaster from "./Toaster.svelte";

	import { mode } from "../../stores";
	import { failed, modeData, GameState } from "../../utils";
	import { getContext } from "svelte";
    import Stat from "./stats/Stat.svelte";

	export let state: GameState;
	const toaster = getContext<Toaster>("toaster");

	function copyStats() {
		if (failed(state))
		{
			toaster.pop("you must win the game first");
		}	
		else
		{
			toaster.pop("Copied");
			if (modeData.modes[$mode].name === "G1")
			{
				navigator.clipboard.writeText("link1");

			}
			else if (modeData.modes[$mode].name === "G2")
			{
				navigator.clipboard.writeText("link2");
			}
			else if (modeData.modes[$mode].name === "G3")
			{
				navigator.clipboard.writeText("link3");
			}
			else if (modeData.modes[$mode].name === "G4")
			{
				navigator.clipboard.writeText("link4");
			}
			else if (modeData.modes[$mode].name === "G5")
			{
				navigator.clipboard.writeText("link5");
			}
			else if (modeData.modes[$mode].name === "G6")
			{
				navigator.clipboard.writeText("link6");
			}
		}
	}
</script>

<div on:click={copyStats} on:keydown={copyStats}>
	<svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24">
		<path
			fill="white"
			d="M4.167 4.167c-1.381 1.381-1.381 3.619 0 5L6.5 11.5a1.18 1.18 0 0 1 0 1.667 1.18 1.18 0 0 1-1.667 0L2.5 10.833C.199 8.532.199 4.801 2.5 2.5s6.032-2.301 8.333 0l3.333 3.333c2.301 2.301 2.301 6.032 0 8.333a1.18 1.18 0 0 1-1.667 0 1.18 1.18 0 0 1 0-1.667c1.381-1.381 1.381-3.619 0-5L9.167 4.167c-1.381-1.381-3.619-1.381-5 0zm5.667 14c-2.301-2.301-2.301-6.032 0-8.333a1.18 1.18 0 0 1 1.667 0 1.18 1.18 0 0 1 0 1.667c-1.381 1.381-1.381 3.619 0 5l3.333 3.333c1.381 1.381 3.619 1.381 5 0s1.381-3.619 0-5L17.5 12.5a1.18 1.18 0 0 1 0-1.667 1.18 1.18 0 0 1 1.667 0l2.333 2.333c2.301 2.301 2.301 6.032 0 8.333s-6.032 2.301-8.333 0l-3.333-3.333z"
		/>
	</svg>
	<h6>link to next step</h6>
</div>

<style lang="scss">
	div {
		color: #fff;
		font-size: var(--fs-medium);
		text-transform: uppercase;
		font-weight: bold;
		background: var(--color-correct);
		border-radius: 4px;
		height: 52px;
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 8px;
		width: 80%;
		cursor: pointer;
		&:hover {
			opacity: 0.9;
		}
	}
</style>
