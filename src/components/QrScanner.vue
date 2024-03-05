<template>

	<div class="scanner">
		<qrcode-stream @detect="onDetect"></qrcode-stream>
	</div>
	<p v-if="content">{{ content }}</p>
	<p>-----------------------------------------</p>
	<p>{{WebApp}}</p>
</template>

<script setup lang="ts">
import { QrcodeStream } from 'vue-qrcode-reader'
import { WebApp } from "@grammyjs/web-app";
import {onMounted, ref} from "vue";
const onDetect = (ctx: object) => {
	content.value = ctx
}
const content = ref<object>({})
const webAppData = ref()
onMounted(() => {
	WebApp.ready()
})
</script>

<style scoped>
.scanner {
	display: flex;
	justify-content: center;
	align-items: center;
	width: 40vh;
	height: 40vh;
}
</style>