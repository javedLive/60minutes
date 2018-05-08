<template>
	<div>
		<h1>Hello World</h1>
		<form @submit.prevent="add">
			<input type="text" v-model="newItem" name="">
			<button type="submit">Add</button>
		</form>
		
		<items :items="lists"></items>
	</div>
</template>
<script type="text/javascript">
import items from './Items';
	export default{

		components : {items},

		data(){
			return {
				lists : [
					{'name' : 'Javed'},
					{'name': 'Hossain'},
					{'name' : 'Ahsan'},
					{'name' : 'Babul'},
				],
				newItem : null
			}
		},
		methods:{
			add(){
				this.lists.push({'name':this.newItem})
				this.newItem = null
			}
		},
			created(){
				EventBus.$on('itemRemove',(index)=>{
					this.lists.splice(index,1)
				})
				
			 }
		
	}
</script>
<style type="text/css">
	
</style>