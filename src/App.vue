<script setup lang="ts">
import { RouterView } from 'vue-router'
import { onMounted } from "vue";
import { WebApp } from "@grammyjs/web-app";
onMounted(() => {
	WebApp.ready()
	// main button settings
	WebApp.expand()
	WebApp.showScanQrPopup({text: 'Scan your QR code'})
	WebApp.MainButton.text = 'Close QR Scanner'
	WebApp.MainButton.isVisible = true
	WebApp.MainButton.onClick(() => WebApp.close())
})
</script>

<template>
	<RouterView />
	<p>!----------------APP DEBUG----------------!</p>
</template>

