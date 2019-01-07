<template>
<div>
  <app-header></app-header>
  <app-videos :videos = "videos"></app-videos>
</div>
</template>

<script>
import Videos from './components/trending/Videos.vue';
import Header from './components/shared/Header.vue';

export default {
  data(){
    return {
      url: `https://video.keyport.io/trending`,
      videos: []
    }
  },
  components: {
    'appVideos': Videos,
    'appHeader': Header
  },
  methods: {
    getTrending(){
      var vm = this;
       fetch(this.url)
        .then(function(res){
              if(!res.ok){
                throw Error();   
              }
              var data = res.json();
              return data;
        })
        .then(function(data){
          data.forEach(function(video){
            // console.log(video);
            vm.videos.push(video);
          })
        })
        .catch(function(err){
          console.log(err);
        }) 
     
    }   

  },
  created(){
    this.getTrending();
    
  }


}
</script>