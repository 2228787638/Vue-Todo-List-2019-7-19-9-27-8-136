<template>
    <div>
        <span @click="change(0)">All</span>
        <span @click="change(1)">Active</span>
        <span @click="change(2)">Complete</span>
    </div>
</template>

<script>
    export default {
        name: "ActiveLabel",
        methods: {
            change(flag) {

                global.status=flag;
                //alert(global.status);
            }
        }
    }
</script>

<style scoped>

</style>
