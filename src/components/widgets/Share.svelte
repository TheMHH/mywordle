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
			// toaster.pop("Copied");
			if (modeData.modes[$mode].name === "G1")
			{
				// navigator.clipboard.writeText("link1");
				toaster.pop("🔑 361", 5);
			}
			else if (modeData.modes[$mode].name === "G2")
			{
				// navigator.clipboard.writeText("link2");
				toaster.pop("🔑 45", 5);
			}
			else if (modeData.modes[$mode].name === "G3")
			{
				// navigator.clipboard.writeText("link3");
				toaster.pop("🔑 323", 5);
			}
			else if (modeData.modes[$mode].name === "G4")
			{
				// navigator.clipboard.writeText("link4");
				toaster.pop("🔑 44", 5);
			}
			else if (modeData.modes[$mode].name === "G5")
			{
				// navigator.clipboard.writeText("link5");
				toaster.pop("🔑 387", 5);
			}
			else if (modeData.modes[$mode].name === "G6")
			{
				// navigator.clipboard.writeText("link6");
				toaster.pop("🔑 87", 5);
			}
			else if (modeData.modes[$mode].name === "G7")
			{
				// navigator.clipboard.writeText("link7");
				toaster.pop("🔑 53", 5);
			}			
			else if (modeData.modes[$mode].name === "G8")
			{
				// navigator.clipboard.writeText("link8");
				toaster.pop("🔑 118", 5);
			}
		}
	}
</script>

<div on:click={copyStats} on:keydown={copyStats}>
	<h6>next step</h6>
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
		width: 50%;
		cursor: pointer;
		&:hover {
			opacity: 0.9;
		}
	}
</style>
