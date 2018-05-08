<template>
<ul>
  <li 
      v-for="(item,index) in items" 
      :key="item.name"
      v-if="item.name !== 'Nazmul' ">
    	{{item.name}} 
    <button @click="remove(index)">X</button>
  </li>
  	<li v-else> No Nazmul Allow Here</li>
</ul>
</template>
<script type="text/javascript">
	export default{
		props:['items'],
		methods:{
			remove(index){
				EventBus.$emit('itemRemove',index)
			}
		}

	}
</script>
<style type="text/css">
	
</style>