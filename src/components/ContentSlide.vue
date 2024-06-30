<script setup lang="ts">
import { computed, useSlots } from 'vue';

const props = withDefaults(defineProps<{
	currentIndex?: number
}>(),  {
	currentIndex: 0
})


const slots = useSlots()

const currentSlot = computed(() => {
	let slot = slots.default!()[props.currentIndex]
	return slot
})
</script>


<template>
	<Transition name="slide" mode="out-in">
		<component :is="currentSlot" :key="currentIndex" />
	</Transition>
</template>

<style scoped>
.slide-enter-active {
	transition-duration: 100ms;
	
}
.slide-enter-from {
	opacity: 0;
	transform: translateX(15px);
}


.slide-leave-active {
	opacity: 0;
	transform: translateX(-15px);
}
.slide-leave-to {
	transition-duration: 100ms;
}

</style>