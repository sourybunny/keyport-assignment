<template>
   
        <p>Posted {{moment(getTime()).fromNow()}}</p>
    
</template>

<script>
var moment = require('moment');
export default {
    data(){
        return {
            moment: moment
        }
    },
    props: ['createdAt'],
    methods: {
        getTime(){
            return this.createdAt;
        }
    }
}
</script>