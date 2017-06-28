<template>
<div class="test">
	<input type="text" v-model="title"><br />
	<h1>{{title}}</h1>
	<p v-if="showName">{{user.firstName}}</p>
	<p v-else="showName">No  body</p>
	<p v-text="user.lastName"> </p>
	<ul>
		<li v-for="item in items">{{item.title}}</li>
	</ul>
	<button v-on:click="greet('Hello World')">Say Greeting</button>
	<br />
	<input type="text" v-on:keyup="pressKey">
	<br />
	<label>First Name: </label><input type="text" v-model="user.firstName"/>
	<label>Last Name: </label><input type="text" v-model="user.lastName"/>
	<br />
	<h3>{{fullName}}</h3>
</div>
</template>

<script>
export default {
	name: 'test',
	data(){
		return {
			title: 'Hello World',
			user:{
				firstName: 'Kuldeep',
				lastName: 'Jadeja'
			},
			showName: true,
			items: [
				{title:'Item One'},
				{title:'Item Two'},
				{title:'Item Three'}
			]
		}
	},
	methods:{
		greet: function(greeting){
			alert(greeting);
		},
		pressKey:function(e){
			alert("hi");
		},		
	},
	computed:{
			fullName:function(){
			return this.user.firstName + ' ' + this.user.lastName;
			}
	}
}
</script>

<style scoped>

</style>