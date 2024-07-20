<script setup lang="ts">
import { ref } from 'vue';

const count = ref(0)

</script>

<script lang="ts">
export default {
	name: "CoolCounter"
}
</script>

<template>
	<button @click="() => count++">Click em mim</button>
	<p> {{ count }} clicks </p>
</template>
