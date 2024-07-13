<script setup lang="ts">
import { computed, useSlots } from 'vue';

// O slide a mostrar é controlado pelos componentes pai
const props = withDefaults(defineProps<{
	currentIndex?: number
	keepAlive?: boolean
}>(),  {
	currentIndex: 0
})

/**
 * Obtendo todos os slots passados para o slide
 */
const slots = useSlots()

/**
 * @returns Slide a renderizar
 */
const currentSlot = computed(() => {
	let slot = slots.default!()[props.currentIndex]
	
	return slot
})
</script>


<template>

	<!-- Transição de entrada e saída para cada item, é algo visual e opcional -->
	<!-- :key é necessário para identificar cada componente -->
	<Transition name="slide" mode="out-in">
		<keep-alive include="CoolCounter">
			<component :is="currentSlot" :key="currentIndex" /> 
		</keep-alive>

	</Transition>
</template>

<style scoped>

.slide-enter-active {
	transition-duration: 100ms;
}
.slide-enter-from {
	opacity: 0;
	transform: translateX(15px) scaleY(0.7);
}

.slide-leave-active {
	opacity: 0;
	transform: translateX(-15px);
}
.slide-leave-to {
	transition-duration: 100ms;
}

</style>