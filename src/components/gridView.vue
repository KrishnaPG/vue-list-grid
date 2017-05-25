<template>
	<div class="row">
		<b-card class="mb-2 gridView-item" v-for="item in data" :img="item.image.small">		
			{{item.title}}
		</b-card>
	</div>
</template>
<script>
	export default 
	{
		name: 'gridView',
		props: {
			'data': { default: () => { } }
		},
		data: function() {
			return { }
		},		
	}
</script>
<style>
	.gridView-item.card
	{	
		margin: 4px;
    border: 2px solid lightblue;
	}
	.listGrid-gridView .row
	{
		margin: 0px;
	}
</style>