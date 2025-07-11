<script setup></script>

<template>
	<div class="ui-search">
		<input
			type="search"
			class="ui-search__input"
			placeholder="Автор, название, ISBN"
		/>
		<button class="ui-search__button">
			<IconsSearch class="ui-search__button-icon" />
			<span class="ui-search__button-text">Искать</span>
		</button>
	</div>
</template>

<style lang="scss" scoped>
.ui-search {
	@include flex(center);
	width: 100%;
	max-width: 570px;

	&__input {
		width: 100%;
		padding: 10px 15px;
		border: 1px solid $border;
		border-right: none;
		border-radius: 5px 0 0 5px;
		outline: none;
	}

	&__button {
		padding: 9px 25px;
		max-height: 40px;
		background-color: $accent;
		border: none;
		border-radius: 0 5px 5px 0;
		@include flex(center, stretch, 5px);
		&-icon {
		}

		&-text {
			color: $white;
		}
	}
}
</style>
