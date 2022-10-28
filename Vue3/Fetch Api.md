import { useFetch } from "@vueuse/core";

const url = "";

const { isFetching, error, data } = await useFetch(url);

**git remote** add upstream [https://github.com/Davros2014/vue-challenge](https://github.com/Davros2014/vue-challenge)

	export default {
		async setUp() {
			try {
				const response = await fetch({baseUrl});
				const data = await response.json();
			}
			catch(err) {
				console.log(err),
			}
		};
	} 

### Using fetch with async/await and suspense


	export default {
	  async setup() {
	    const res = await fetch(...)
	    const posts = await res.json()
	    return {
	      posts
	    }
	  }
	}

	async setup() {
		const { data, error, isFetching } = await useFetch(baseUrl, {refetch}).get();
		const notes = await data.json();
		return notes;
	};