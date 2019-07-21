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
                let id = global.items.length+1;
                let objs={"id":id,"name":this.msg,"active":false,"editFlag":true};
                global.items.push(objs);
                this.msg="";
            }
        }
    }
</script>

<style scoped>

</style>
