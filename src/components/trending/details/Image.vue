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

<style>
img {
        background-color: #ccc;
        display: block;
        margin: 0;
        max-width: 100%;
        min-height: 238px;
        min-width: 100%;
        border-top-left-radius: 6px;
        border-top-right-radius: 6px;
        
   
}
.image {
        position: relative;
}
</style>
