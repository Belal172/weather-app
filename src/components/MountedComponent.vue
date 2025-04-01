<template>
<h1>Mounted and beforeMount {{ msg }}</h1>
</template>

<script>
export default {
    name: 'MountedComponent',
    data() {
        return {
            msg: "milan hello"
        }
    },
    beforeMount() {
        console.log("beforeMount: Template is compiled but not in the DOM" ,this.$el);
    },
    mounted() {
        console.warn("Mounted", this.$el)
    }
}
</script>
