<template>
  <div class="container border text-center">
	  <h3 class="mt-2">Mis Repos</h3>
	  <img :src="gitPp" alt="" width="200" class="rounded">
	  <hr>
	  <loader v-if="isLoading"/>
	  <div class="container">
		<div class="row py-4 g-2">
			<div v-for="project in misProyectos" :key="project.id" 
			class="col-sm-6">
				<Card :repoTitle="project.name" 
				:repoDescription="project.description" 
				:repoDate="project.created_at.substring(0,4)"
				:repoUrl="project.html_url"
				:homeUrl="project.homepage"
				/>
			</div>
		</div>
	  </div>
  </div>
</template>

<script>
import Card from './Card.vue'
import Loader from './Loader.vue'

export default {
	components: { Card, Loader },
	data(){
			return{
				misProyectos: null,
				gitPp: null,
				isLoading: false
			}
		},
	methods: {
			async getRepos(){
				this.isLoading = true;
				const response = await fetch("https://api.github.com/users/dr-madrix/repos");
				const data = await response.json();


				data.sort(function(a,b){
					return b.created_at.substring(0,4) - a.created_at.substring(0,4)
				})

				this.misProyectos = data;
				this.gitPp = await data[0].owner.avatar_url
				this.isLoading = false;
				console.log(this.misProyectos);

			}
		},
	created(){
		this.getRepos();
	}
}
</script>

<style>

</style>