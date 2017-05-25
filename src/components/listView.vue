<template>
	<b-table striped hover :items="data" :fields="columns">
		<template slot="image" scope="item">
				<img :src="item.value.small" width="32" height="32"/>
		</template>
	</b-table>	
</template>
<script>
	export default {
		name: 'listView',		
		props: {
			'data': { default: () => { } }
		},
		data: function() {
			return { }
		},
		computed: {
			tableData: function() { return this.data; },
			columns: function() {
				return {
					title: {label: 'Title'},
					url: {label:'URL'},
					image: {label: 'Image'}
				}
			}
		}
	}
</script>