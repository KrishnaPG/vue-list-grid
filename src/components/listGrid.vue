<template>
	<div class="listGrid">
		<div class="listGrid-toolbar"></div>
		<div class="listGrid-body">
			<div v-if="view=='list'" class="listGrid-listview">
				<ul>
					<li v-for="dataItem in data">{{dataItem.title}}, {{dataItem.url}}</li>
				</ul>
				<component :is="listRenderer" :data="data"></component>
			</div>
			<div v-if="view=='grid'" class="listGrid-gridView">
				<component :is="gridRenderer"></component>
			</div>
		</div>		
	</div>
</template>
<script>
	export default {
		name: 'listGrid',
		props: {
			'view': { type: String, default: 'list' },
			'data': { default: () => {}	},
			'listRenderer': { default: () => { } },
			'gridRenderer': { default: () => { } }
		},
		data: function() {
			return {
			}
		},
	}
</script>