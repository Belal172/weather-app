<template>
<h1 ref="count"> {{ counter }}</h1>
<button v-on:click="counter=counter+1">Update counter</button>
</template>
<script>
export default{
    name:'UpdatedComponent',
    data(){
        return{
            counter:0
        }
    },
    beforeUpdate(){
        console.log("beforeupdate:",this.$refs['count'].textContent);
    },
    updated(){
        console.log("updated:",this.$refs['count'].textContent)
    }
}
</script>