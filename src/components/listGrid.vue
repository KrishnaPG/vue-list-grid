<template>
	<div class="listGrid">
		<div class="listGrid-toolbar">
			<span class="listGrid-caption">{{caption}}</span>
			<span class="listGrid-switch-iconGroup">
				<i class="fa fa-list listGrid-switch-icon" 
					v-bind:class="{ active: currentView=='list'}" 
					aria-hidden="true"
					:title="currentView=='grid' ? 'switch to List View': 'List View'"
					 v-on:click="switchToListView"></i>
				<i class="fa fa-th listGrid-switch-icon" 
					v-bind:class="{ active: currentView=='grid'}" 
					:title="currentView=='list' ? 'switch to Grid View': 'Grid View'"
					aria-hidden="true" v-on:click="switchToGridView"></i>				
			</span>
		</div>
		<div class="listGrid-body">
			<div v-if="currentView=='list'" class="listGrid-listview">
				<component :is="listRenderer" :data="data"></component>
			</div>
			<div v-if="currentView=='grid'" class="listGrid-gridView">
				<component :is="gridRenderer" :data="data"></component>
			</div>
		</div>		
	</div>
</template>
<script>
	export default {
		name: 'listGrid',
		props: {
			'caption': { type:String, default: '' },
			'view': { type: String, default: 'list' },
			'data': { default: () => {}	},
			'listRenderer': { default: () => { } },
			'gridRenderer': { default: () => { } }
		},
		data: function() {
			return {	
				currentView: this.view	//initially set to same value as prop			
			}
		},
		methods: {
			switchToListView: function(ev)
			{
				this.currentView = 'list';
			},
			switchToGridView: function(ev)
			{
				this.currentView = 'grid';
			}
		}
	}
</script>
<style>
	.listGrid
	{
		margin: 4px;
	}	
	.listGrid-caption
	{
		font-weight: bold;
	}
	.listGrid-toolbar
	{
		width: 100%;
		height: 32px;
		line-height: 32px;
		background-color: lightgray;
		padding-left: 8px;
	}
	.listGrid-switch-iconGroup
	{
		float: right;
		padding-right: 8px;
		padding-left: 8px;
	}
	.listGrid-switch-icon
	{
		padding: 4px;		
		border-radius: 4px;
		background-color: transparent;
		cursor: pointer;
	}
	.listGrid-switch-icon.active
	{
		background-color: lavender;
		cursor: default;
	}
</style>