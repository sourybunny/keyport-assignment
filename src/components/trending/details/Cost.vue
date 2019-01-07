<template>
    <p><strong>{{getCost()}}</strong> </p>
</template>

<script>
export default {
    props: ['minutes','costperminute'],
    methods: {
        getCost(){
            var cost = this.costperminute*this.minutes;
            
            return "$ "+cost.toFixed(2);

        }
    }
}
</script>
