<template>
	<button class="qr-button" @click="showScannerPopup">Open again</button>
	<p>{{context}}</p>
</template>

<script setup lang="ts">
import {onMounted, ref} from "vue";
import { WebApp } from "@grammyjs/web-app";
const context = ref<string>('')
const showScannerPopup = () => {
	WebApp.showScanQrPopup({text: 'Scan your QR code! :)'}, async (data: string) => {
		context.value = data
	})
}

onMounted(() => {
	WebApp.
	WebApp.ready()
	// main button settings
	showScannerPopup()
	context.value.length > 0 && WebApp.expand()
	WebApp.MainButton.text = 'Close QR Scanner'
	WebApp.MainButton.isVisible = true
	WebApp.MainButton.onClick(() => WebApp.close())
})
</script>