<template>
	<v-data-table :data='loadData' :columns='columns'></v-data-table>
</template>
<script>
	export default {
		name: 'listComponent',		
		props: {
			'data': { default: () => { } }
		},
		data: function() {
			return {
			}
		},
		computed: {
			loadData: function() { let self = this; return () => { self.data; }
			},
			columns: function() {
				return [
					{title: 'Title', field: 'title'},
					{title: 'URL', field: 'url'},
					{title: 'Image', field: 'image.large'}
				]
			}
		}
	}
</script>