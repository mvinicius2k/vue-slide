<script setup lang="ts">
import { ref } from 'vue';
import ContentSlide from './components/ContentSlide.vue';
import ContentSlideItem from './components/ContentSlideItem.vue'
import CoolCounter from './components/CoolCounter.vue';

const slideIndex = ref(0)

</script>

<template>

	<!-- Contêiner centralizado do conteúdo -->
	<div class="page-container">

		<!-- Contêiner dos slides -->
		<div class="slide-container">
			<ContentSlide :current-index="slideIndex">
				<ContentSlideItem>
					<CoolCounter/>
				</ContentSlideItem>
				<ContentSlideItem>
					<p> Voluptate consequat fugiat in est occaecat ex duis. </p>
				</ContentSlideItem>
				<ContentSlideItem>
					<img src="/ra.jpg"/>
				</ContentSlideItem>
			</ContentSlide>

		</div>

		<!-- Contêiner dos botões -->
		<div>
			<button @click="() => slideIndex--"> <<	</button>
			{{ slideIndex }}
			<button @click="() => slideIndex++"> >> </button>
		</div>
		
	</div>

</template>

<style scoped>
.slide-container {
	width: 500px;
	height: 350px;
	border: 1px silver solid;
	overflow-x: hidden;
	overflow-y: auto;
	padding: 10px;
	margin: 5px;
}

.page-container{
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	height: 100vh;
}

img{
	width: 100%;
}


</style>
