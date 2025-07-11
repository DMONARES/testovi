<script setup>
const props = defineProps({
	linkIconsLeft: {
		type: Array,
	},
	linkIconsRight: {
		type: Array,
	},
});
</script>

<template>
	<div class="info-block">
		<div class="container info-block__wrapper">
			<div class="info-block__left info-block__side">
				<UiLink
					v-for="(item, index) in linkIconsLeft"
					:key="index"
					:icon="item.icon"
					:info="item.info"
					:link="item.link"
					class="info-block__link"
				>
					{{ item.text }}
				</UiLink>
			</div>
			<div class="info-block__right info-block__side">
				<UiLink
					v-for="(item, index) in linkIconsRight"
					:key="index"
					:icon="item.icon"
					:info="item.info"
					:link="item.link"
					class="info-block__link"
				>
					{{ item.text }}
				</UiLink>
			</div>
		</div>
	</div>
</template>

<style lang="scss" scoped>
.info-block {
	padding-block: 15px;
	gap: 30px;
	border-bottom: 1px solid $border;

	&__wrapper {
		@include flex(center, space-between);
		width: 100%;
	}

	&__side {
		@include flex(center, stretch, 20px);
	}

	&__left,
	&__right {
		@include flex(center, stretch, 20px);
	}
}
</style>
