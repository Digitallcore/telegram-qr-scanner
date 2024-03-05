<script setup lang="ts">
import { RouterView } from 'vue-router'
import { onMounted } from "vue";
import { WebApp } from "@grammyjs/web-app";
onMounted(() => {
	WebApp.ready()
	// main button settings
	WebApp.MainButton.text = 'Close QR Scanner'
	WebApp.MainButton.isVisible = true
	WebApp.MainButton.onClick(() => WebApp.close())
})
</script>

<template>
	<RouterView />
	<p>!----------------DEBUG----------------!</p>
</template>

