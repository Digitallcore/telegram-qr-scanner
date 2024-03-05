<template>
	<button class="qr-button" @click="showScanPopup">Start scanning QR codes!</button>
	<p>!---Debug---!</p>
	<p>{{context}}</p>
</template>

<script setup lang="ts">
import {onMounted, ref} from "vue";
import { WebApp } from "@grammyjs/web-app";
const context = ref<string>('')
const showScanPopup = () => {
	WebApp.showScanQrPopup({text: 'Scan your QR code! :)'}, async (data: string) => {
		context.value = data
	})
}

onMounted(() => {
	WebApp.ready()
	// main button settings
	WebApp.expand()
	WebApp.MainButton.text = 'Close QR Scanner'
	WebApp.MainButton.isVisible = true
	WebApp.MainButton.onClick(() => WebApp.close())
})
</script>

<style scoped>
.qr-button {
	display: flex;
	align-items: center;
	justify-content: center;
	background: #f2f2f2;
	border: 1px solid black;
}
</style>