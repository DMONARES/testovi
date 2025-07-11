<script setup>
import IconsLocation from "@/components/icons/location.vue";
import IconsShipping from "@/components/icons/shipping.vue";
import IconsAddress from "@/components/icons/address.vue";
import IconsEmail from "@/components/icons/email.vue";
import IconsPhone from "@/components/icons/phone.vue";

const linkIconsLeft = [
	{
		icon: IconsLocation,
		text: "Москва",
		info: false,
	},
	{
		icon: IconsShipping,
		text: "Доставка и оплата",
		info: false,
	},
	{
		icon: IconsAddress,
		text: "Адрес и часы работы",
	},
];
const linkIconsRight = [
	{
		icon: IconsEmail,
		text: "market@estatut.ru",
		link: "mailto:market@estatut.ru",
	},
	{
		icon: IconsPhone,
		text: "8 (968) 660-65-50",
		info: true,
		link: "89686606550",
	},
];
</script>

<template>
	<div class="default-layout">
		<InfoBlock
			:linkIconsLeft="linkIconsLeft"
			:linkIconsRight="linkIconsRight"
			class="mobile-hidden"
		/>
		<Header />
		<main>
			<slot />
		</main>
	</div>
</template>

<style lang="scss"></style>
