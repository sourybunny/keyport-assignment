<template>
   
        <p>{{getDuration()}}</p>
    
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