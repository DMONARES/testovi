<script setup>
const props = defineProps({
	prev: {
		type: Boolean,
		default: false,
	},
	next: {
		type: Boolean,
		default: false,
	},
});
</script>

<template>
	<button class="nav-button">
		<IconsNavArrow
			class="nav-button__button"
			:class="{
				'nav-button__button--prev': prev,
				'nav-button__button--next': next,
			}"
		/>
	</button>
</template>

<style lang="scss" scoped>
.nav-button {
	padding: 10px;
	background-color: $white;
	border-radius: 5px;
	transition: all 0.3s ease;
	cursor: pointer;

	&:hover {
		background-color: $lightGray;
	}

	&:disabled {
		opacity: 0.5;
		cursor: not-allowed;
	}

	&__button {
		&--prev {
			rotate: 180deg;
		}
	}
}
</style>
