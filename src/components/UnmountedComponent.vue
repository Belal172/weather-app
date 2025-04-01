<template>
    <h1>unmounted </h1>
</template>

<script>
export default{
    name:'UnmountedComponent',
    beforeUnmount() {
    console.log("beforeUnmount: Cleanup before component is removed");
  },
  unmounted() {
    console.log("unmounted: Component is completely removed from DOM");
  }
}
</script>