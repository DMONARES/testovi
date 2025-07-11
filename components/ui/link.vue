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
	isCount: {
		type: Boolean,
		default: false,
	},
	count: {
		type: Number,
		default: 0,
	},
	accent: {
		type: Boolean,
		default: false,
	},
});
</script>

<template>
	<div class="ui-link">
		<div v-if="icon" class="ui-link__icon">
			<component :is="icon" class="ui-link__icon" />
			<span v-if="isCount">{{ count }}</span>
		</div>
		<a
			:href="link"
			class="ui-link__text"
			:class="{ 'ui-link__text--accent': accent }"
		>
			<slot />
		</a>
		<IconsInfo v-if="info" class="ui-link__info" />
	</div>
</template>

<style lang="scss" scoped>
.ui-link {
	position: relative;
	width: max-content;
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
		position: relative;
		width: 20px;
		height: 20px;
		fill: currentColor;

		span {
			position: absolute;
			top: -5px;
			right: -7px;
			width: 15px;
			height: 15px;
			font-size: 9px;
			line-height: 15px;
			color: $white;
			background-color: $accent;
			border-radius: 50%;
			@include flex(center, center);
		}
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

		&--accent {
			color: $red;
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
