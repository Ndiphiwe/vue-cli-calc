<template>
  <button @click="add" class="btn-dark">{{operator}}</button>
</template>

<script>
export default {
    props: ['operator'],
    methods: {
        add(){
            this.$emit("add")
        }
    },
}
</script>

<style>

</style>