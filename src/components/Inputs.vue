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
                alert(id);
                let objs={"id":id,"name":this.msg,"active":false};
                global.items.push(objs);
                alert(global.items[id].name);
            }
        }
    }
</script>

<style scoped>

</style>
