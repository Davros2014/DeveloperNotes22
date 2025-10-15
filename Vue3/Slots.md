

If we create a template 'card' say BaseCard.vue, we can register that in main.js like so - import BaseCard from './components/BaseCard.vue' & attach as a component app.component('base-card', BaseCard);	




	// in BaseCard.vue
	
	<template>
		  <section>
			  // slot allows any content to be placed between the container you create
			<slot/>
		 </section>
	</template>


	<style scoped>
	...some styles
	</style>

// then enter content in the component you wish to use the BaseCard.vue template as so 

	<base-card>
		... your html content
	</base-card>

