<template>
    <div>
        <input v-model="msg" type="text" name="additem">
        <button @click="add">add</button>
    </div>
</template>

<script>
    import global from '../common.vue';
    export default {
        name: "Inputs",
        data(){
            return {
                msg:""
            }
        },
        methods:{
            add(){
                global.items.push({"name":this.msg,"active":false});
            }
        }
    }
</script>

<style scoped>

</style>
