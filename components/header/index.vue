<script setup>
import IconsMark from "@/components/icons/mark.vue";
import IconsSmile from "@/components/icons/smile.vue";
import IconsCart from "@/components/icons/cart.vue";
import IconsMenu from "@/components/icons/menu.vue";
import IconsSale from "@/components/icons/sale.vue";

const links = [
	{ icon: IconsMark, text: "Отложено" },
	{ icon: IconsSmile, text: "Войти" },
	{ icon: IconsCart, text: "Корзина", isCount: true, count: 10 },
];

const navLinks = [
	{ icon: IconsMenu, text: "Каталог" },
	{ text: "Авторы" },
	{ text: "Новинки" },
	{ icon: IconsSale, text: "Скидки", accent: true },
	{ text: "Партнёрам" },
	{ text: "Мы" },
];
</script>

<template>
	<div class="container">
		<header class="header">
			<div class="header__content">
				<div class="header__content-left">
					<IconsLogo class="header__content-logo" />
					<UiSearch class="header__content-search" />
				</div>
				<div class="header__content-right">
					<UiLink
						v-for="(item, index) in links"
						:key="index"
						:icon="item.icon"
						:isCount="item.isCount"
						:count="item.count"
					>
						{{ item.text }}
					</UiLink>
				</div>
			</div>
			<nav class="header__menu">
				<ul class="header__menu-list">
					<li
						class="header__menu-item"
						v-for="(item, index) in navLinks"
						:key="index"
					>
						<UiLink
							:icon="item.icon"
							:isCount="item.isCount"
							:accent="item.accent"
							:count="item.count"
						>
							{{ item.text }}
						</UiLink>
					</li>
				</ul>
			</nav>
		</header>
	</div>
</template>

<style lang="scss" scoped>
.header {
	width: 100%;
	padding-block: 20px;
	@include flex(flex-start, space-between, 20px, column);

	&__content {
		width: 100%;
		@include flex(center, space-between, 30px);

		&-left {
			@include flex(center, space-between, 30px);
		}
		&-right {
			@include flex(center, space-between, 30px);
		}
	}
	&__menu {
		&-list {
			@include flex(center, stretch, 25px);
		}
	}
}
</style>
