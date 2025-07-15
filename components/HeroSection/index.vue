<script setup>
import IconsBlockMini1 from "@/components/icons/block-mini-1.vue";
import IconsBlockMini2 from "@/components/icons/block-mini-2.vue";
import IconsDecor1 from "@/components/icons/decor-1.vue";
import IconsDecor2 from "@/components/icons/decor-2.vue";

const slides = [
	{ image: "/img/slider-image.png" },
	{ image: "/img/slider-image.png" },
	{ image: "/img/slider-image.png" },
];

const blocksMini = [
	{
		decorText: "Бесплатно",
		decorIcon: IconsDecor1,
		text: "доставим ваш заказ при покупке от 2000 ₽",
		image: IconsBlockMini1,
		default: true,
	},
	{
		decorText: "15%",
		decorIcon: IconsDecor2,
		text: "Скидка <br> при регистрации до",
		image: IconsBlockMini2,
		default: false,
	},
];
</script>

<template>
	<div class="hero-section">
		<Slider :slides="slides" />
		<InfoBlockMini
			:blockMini="item"
			v-for="(item, index) in blocksMini"
			:key="index"
		/>
	</div>
</template>

<style lang="scss" scoped></style>
