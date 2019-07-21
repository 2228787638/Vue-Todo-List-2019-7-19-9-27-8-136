<template>
    <div>
        <div v-for="item in items">
            <div v-if="status===0||status===1&&item.active===false||status===2&&item.active===true">
                {{item.id}}.<label v-bind:class="{changeCheckbox:item.active}" v-on:dblclick="changeContent(item.id,item.name)">
                <input type="checkbox" v-model="item.active"/>
                <span v-if="item.editFlag">{{item.name}}</span>
                <span v-else><input v-model="item.name" type="text" @keyup.enter="enterClick(item.id)"></span>
                </label>
            </div>
        </div>
        <span @click="change(0)">All</span>
        <span @click="change(1)">Active</span>
        <span @click="change(2)">Complete</span>
    </div>
</template>

<script>
    /* eslint-disable vue/no-shared-component-data,no-unused-vars,no-console,no-undef */
    import global from '../common.vue';
    export default {
        name: "Item",
        data(){
            return {
                items:global.items,
                status:global.status
            }
        },
        methods: {
            change(flag) {
                this.status=flag;
                global.status=flag;
                //alert(global.status);
            },
            changeContent(id,name){
                this.items[id-1].editFlag=false;
            },
            enterClick(id){
                this.items[id-1].editFlag=true;
            }
        }
    }

</script>

<style scoped>
    @import '../common.css';
</style>
