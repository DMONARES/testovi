<script setup>
const props = defineProps({
	icon: {
		type: [String, Object],
		default: null,
	},
	info: {
		type: Boolean,
		default: false,
	},
	link: {
		type: String,
		default: "#",
	},
});
</script>

<template>
	<div class="ui-link">
		<component :is="icon" class="ui-link__icon" />
		<a :href="link" class="ui-link__text">
			<slot />
		</a>
		<IconsInfo v-if="info" class="ui-link__info" />
	</div>
</template>

<style lang="scss" scoped>
.ui-link {
	position: relative;
	transition: all 0.3s ease;
	cursor: pointer;
	@include flex(center, stretch, 5px);

	&:hover {
		.ui-link__text {
			&::after {
				width: 100%;
			}
		}
	}

	&__icon {
		width: 20px;
		height: 20px;
		fill: currentColor;
	}

	&__text {
		position: relative;
		font-size: 14px;
		color: $text;

		@include tablet() {
			font-size: 12px;
		}

		&::after {
			content: "";
			position: absolute;
			bottom: 0;
			left: 0;
			right: 0;
			width: 0;
			height: 1px;
			background-color: $text;
			transition: all 0.3s ease;
		}
	}

	&__info {
		width: 16px;
		height: 16px;
		fill: currentColor;
		cursor: pointer;
	}
}
</style>
