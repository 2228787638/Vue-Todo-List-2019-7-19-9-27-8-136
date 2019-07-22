<template>
    <div>
        <input v-model="msg" type="text" id="additem">
        <button class="btn" @click="add">Add</button>
    </div>
</template>

<script>
    // import global from '../common.vue';
    export default {
        name: "Inputs",
        data(){
            return {
                msg:""
            }
        },
        methods:{
            add(){
                let id = this.$store.state.items.length+1;
                let objs={"id":id,"name":this.msg,"active":false,"editFlag":true};
                this.$store.commit('addItems',objs);
                //this.$store.state.items.push(objs);
                this.msg="";
            }
        }
    }
</script>

<style scoped>

</style>
