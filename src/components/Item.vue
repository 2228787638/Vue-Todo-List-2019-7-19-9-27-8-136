<template>
    <div>
        <div v-for="(item,index) in items">

            <div class="itemstyle">
                {{index+1}}.
                <input type="checkbox" v-model="item.active"/>
                <label v-bind:class="{changeCheckbox:item.active}" v-on:dblclick="changeContent(item.id,item.name)">
                <span v-if="item.editFlag">{{item.name}}</span>
                <span v-else><input v-model="item.name" type="text" @keyup.enter="enterClick(item.id)"></span>
                </label>
            </div>
        </div>
        <ul class="footer">
            <li @click="change(0)" :class="{active:categoryIndex==0}">All</li>&nbsp;&nbsp;
            <li @click="change(1)" :class="{active:categoryIndex==1}">Active</li>&nbsp;&nbsp;
            <li @click="change(2)" :class="{active:categoryIndex==2}">Complete</li>
        </ul>
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
                status:global.status,
                categoryIndex: 0
            }
        },
        methods: {
            change(flag) {
                this.status=flag;
                global.status=flag;
                this.categoryIndex = flag;
                switch (flag) {
                    case 0:this.items=global.items;break;
                    case 1:this.items=global.items.filter(i=>{return !i.active});break;
                    case 2:this.items=global.items.filter(i=>{return i.active});break;
                }

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
