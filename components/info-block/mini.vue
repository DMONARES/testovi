<script setup>
const props = defineProps({
	blockMini: {
		type: Object,
		required: true,
	},
});
</script>

<template>
	<div class="block-mini" v-if="blockMini.default">
		<div class="block-mini__text">
			<span>
				{{ blockMini.decorText }}
				<component :is="blockMini.decorIcon" />
			</span>
			<span> {{ blockMini.text }} </span>
		</div>
		<div class="block-mini__icon">
			<component :is="blockMini.image" />
		</div>
	</div>

	<div
		v-else
		class="block-mini"
		:class="{ 'block-mini--pink': !blockMini.default }"
	>
		<div class="block-mini__text">
			<span v-html="blockMini.text"></span>
			<span>
				{{ blockMini.decorText }}
				<component :is="blockMini.decorIcon" />
			</span>
		</div>
		<div class="block-mini__icon">
			<component :is="blockMini.image" />
		</div>
	</div>
</template>

<style lang="scss" scoped>
.block-mini {
	padding: 20px 25px;
	width: max-content;
	max-width: 360px;
	@include flex(center, stretch, 4px);
	border-radius: 5px;
	background-color: #6d378f;

	&--pink {
		background-color: #ffd8ef;

		span { color: $text !important; }
	}

	&__text {
		span {
			font-family: $secondFont;
			font-size: 20px;
			line-height: 25px;
			color: $white;
			position: relative;
			z-index: 1;
		}

		svg {
			position: absolute;
			top: 50%;
			right: 50%;
			translate: 50% -50%;
			z-index: -1;
		}
	}
}
</style>
