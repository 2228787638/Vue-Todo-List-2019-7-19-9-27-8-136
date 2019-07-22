<template>
    <div>
        <div v-for="item in this.$store.state.items" :key="item.id">
            <div v-if="this.$store.state.status===0||this.$store.state.status===1
            &&item.active===false||this.$store.state.status===2&&item.active===true" class="itemstyle">
                {{id}}.
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
                id:1,
                // items:this.$store.state.items,
                // status:this.$store.state.status,
                categoryIndex: 0
            }
        },
        methods: {
            change(flag) {
                this.$store.commit('changeStatus',flag);
                // this.status=flag;
                // this.$store.state.status=flag;

                this.categoryIndex = flag;
                this.id=1;
            },
            changeContent(id,name){
                this.$store.commit('changeEditFlag',id-1);
                //this.items[id-1].editFlag=false;
            },
            enterClick(id){
                this.$store.commit('enterClick',id-1);
                //this.items[id-1].editFlag=true;
            }
        }
    }

</script>

<style scoped>
    @import '../common.css';

</style>
