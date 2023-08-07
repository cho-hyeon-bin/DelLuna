<template>
	<header>
		<div data-header_btn="left" :data-visibled="current_route.meta.page_back_btn + ''">
			<router-link to="" @click="historyBackSetting" data-btn="">뒤로가기</router-link>
		</div>
		<h1 data-test>
			<span v-if="current_route.meta.header_fixed">
			{{ current_route.meta.header_title !== "" ? current_route.meta.header_title : common_store.header_title }}
			</span>
		</h1>
		<div data-header_btn="right" v-if="!current_route.meta.header_fixed && !current_route.meta.header_home">
			<router-link to="" data-logo></router-link>
			<Notice :img_type = "'home'"/>
		</div>
		<div data-header_btn="right" data-home v-else>
			<router-link to="/"></router-link>
		</div>
	</header>
</template>
<style scoped lang="sass">
</style>
<script setup>
import { useRouter } from "vue-router";
import { commonStore } from "@store/common_store";
</script>