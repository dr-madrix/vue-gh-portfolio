<template>
  <div class="container border text-center">
	  <h3 class="mt-2">Mis Proyectos</h3>
	  <img :src="gitPp" alt="" width="150" class="rounded">
	  <hr>
	  <loader v-if="isLoading"/>
	  <div class="row">
		   <Card v-for="project in misProyectos" :key="project.id" 
		   :repoTitle="project.name" 
		   :repoDescription="project.description" 
		   :repoDate="project.created_at.substring(0,4)"
		   :repoUrl="project.html_url"
		   :homeUrl="project.homepage"

		   class="col-sm-6 mx-auto mt-2"/>
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