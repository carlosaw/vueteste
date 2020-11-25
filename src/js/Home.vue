<template>
	<div>
		<span>Página HOME: {{ t }}</span>
		<br/><br/>

		<span>IP: {{ ip }}</span>

		<ul>
			<li>
				<router-link to="/user/1">Usuário 1</router-link> -
				<router-link to="/user/1/perfil">Perfil</router-link> -
				<router-link to="/user/1/posts">Posts</router-link>
			</li>
			<li>
				<router-link to="/user/2">Usuário 2</router-link> -
				<router-link to="/user/2/perfil">Perfil</router-link> -
				<router-link to="/user/2/posts">Posts</router-link>
			</li>
		</ul>
		
	</div>
</template>

<script>
import axios from 'axios';

export default {
	data() {
		return {
		t:"Carlos Sampaio",
		ip:'Carregando...'
		}
	},
	mounted() {
		axios
			.get('http://ip.jsontest.com')
			.then((r)=>{
				this.ip = r.data.ip;
			});
	}
}
</script>

<style>
	span {
		color: #FF0000;
	}
</style>