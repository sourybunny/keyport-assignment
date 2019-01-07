<template>
   <img :src="src" @mouseover="getGif" @mouseout="getThumbnail"/>
</template>

<script>
export default {
    data(){
        return {
            src: null
        }
    },
    props: ['playbackId','thumbnailToken', 'gifToken'],

    methods: {
        getThumbnail(){
            var imgsrc = "https://image.mux.com/"+this.playbackId+"/thumbnail.png?token="+this.thumbnailToken;
            this.src = imgsrc;
            // console.log(imgsrc)
        },
        getGif(){
            var gifsrc = "https://image.mux.com/"+this.playbackId+"/animated.gif?token="+this.gifToken
            this.src = gifsrc;
        }
        
    },
    created(){
        this.getThumbnail()
        
    }
}
</script>
