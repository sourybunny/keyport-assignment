<template>
    <div class="videoItem">
      
        <img :src="src" @mouseover="getGif" @mouseout="getThumbnail"/>
        <p>{{video.title}}</p>
        <p>{{video.channelName}}</p>
        <p>duration: {{getDuration()}}</p> 
        <p>{{getCost()}}</p>
        <p>Posted {{moment(getTime()).fromNow()}}</p>
    </div>
</template>

<script>
var moment = require('moment');
export default {
    data(){
        return {
            src: null,
            moment:moment,
            minutes: null
            
            
            
        }
    },
    props: ['video'],
    methods: {
        getThumbnail(){
            var imgsrc = "https://image.mux.com/"+this.video.playbackId+"/thumbnail.png?token="+this.video.thumbnailToken;
            this.src = imgsrc;
            // console.log(imgsrc)
        },
        getGif(){
            var gifsrc = "https://image.mux.com/"+this.video.playbackId+"/animated.gif?token="+this.video.gifToken
            this.src = gifsrc;
        },
        getTime(){
            return this.video.createdAt;
        },
        getDuration(){
            this.video.duration;
            var seconds = this.video.duration;
            var date = new Date(seconds * 1000);
            var hh = date.getUTCHours();
            var mm = date.getUTCMinutes();
            this.minutes = seconds/60;
            var ss = date.getSeconds();
            if (hh < 10) {hh = "0"+hh;}
            if (mm < 10) {mm = "0"+mm;}
            if (ss < 10) {ss = "0"+ss;}
            return hh+":"+mm+":"+ss;
        },
        getCost(){
            var cost = this.video.costPerMinute*this.minutes;
            return "$"+cost.toFixed(2);
        }
        
    },
    created(){
        this.getThumbnail()
        
    }
}
</script>

<style>

.videoItem {
    margin: 2%;
    width: 20%;
    text-align: center;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.15);
}
.videoItem img {
    width:100%;
    height: 260px;
}
</style>
