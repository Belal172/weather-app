<template>
<h1>lifecycle creared() method</h1>
<h2>Before created {{ msg }}</h2>
</template>

<script>
export default {
    name: 'CreatedComponent',
    data() {
        return {
            msg:"Milan"

        }
    },
    beforeCreate() {
        this.msg="belal";//no change in msg variable
        console.warn("before created run")

    },
    created() {
        alert("milan")
        console.warn("created fun run");
        this.msg="Hello from here"
    }
}
</script>
