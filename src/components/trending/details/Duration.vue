<template>
   
        <p class= "duration">{{getDuration()}}</p>
    
</template>

<script>
export default {
    
    props: ['duration'],
    methods: {
        getDuration(){
            
            var seconds = this.duration
            var date = new Date(seconds * 1000);
            var hh = date.getUTCHours();
            var mm = date.getUTCMinutes();
            var ss = date.getSeconds();
            if (hh < 10) {hh = "0"+hh;}
            if (mm < 10) {mm = "0"+mm;}
            if (ss < 10) {ss = "0"+ss;}
            return hh+":"+mm+":"+ss;
        }
    }
}
</script>

<style>
.duration {
        background-color: rgba(0,0,0,0.5);
        color:antiquewhite;
        padding: 4px;
        border-radius:5%;
        margin: 0;
        position: absolute;
        transform: translate(354%,-101%)
    
}
</style>
