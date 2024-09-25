

To pass data from the parent element to any child component that might be deeply nested within many other child elements

	// in ChildComponentToProvideTo.vue
	
	<script>
		export default {
			inject: ['topics']
		}
	</script>
	
	// in app.vue

	<script>
		export default {
		data() {
			return {
				topics: [
					{
					id: 'idName',
					name: 'SomeName'
					...rest of object info...		
					}
				]
			}
		}
		provide() {
			return {
				topics: this.topics
			}
		}
	}
	</script>

