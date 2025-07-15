<script setup>
const containerRef = ref(null);
const swiper = useSwiper(containerRef);

const props = defineProps({
	slides: {
		type: Array,
		required: true,
	},
});
</script>

<template>
	<div class="ui-slider">
		<ClientOnly>
			<swiper-container ref="containerRef" class="ui-slider__wrapper">
				<swiper-slide
					v-for="(slide, index) in slides"
					:key="index"
					class="ui-slider__slide"
				>
					<img :src="slide.image" class="ui-slider__slide-image" />
				</swiper-slide>
			</swiper-container>
		</ClientOnly>

		<div class="ui-slider__nav">
			<UiNavButton prev @click="swiper.prev()" class="ui-slider__nav-button">
				Prev
			</UiNavButton>
			<UiNavButton next @click="swiper.next()" class="ui-slider__nav-button">
				Next
			</UiNavButton>
		</div>
	</div>
</template>

<style lang="scss">
.ui-slider {
	position: relative;
	max-width: 750px;

	&__wrapper { pointer-events: auto; }

	&__nav {
		position: absolute;
		top: 50%;
		translate: 0 -50%;
		width: 100%;
		padding-inline: 30px;
		display: flex;
		align-items: center;
		justify-content: space-between;
		z-index: 10;
		pointer-events: none;

		&-button { pointer-events: auto; }
	}
}
</style>
