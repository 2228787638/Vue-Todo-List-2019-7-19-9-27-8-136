<template>
    <div>
        <div v-for="item in items">
            <div v-if="status===0">
                {{item.id}}.<label v-bind:class="{changeCheckbox:item.active}">
                    <input type="checkbox" v-model="item.active"/>{{item.name}}
                </label>
            </div>
            <div v-else-if="status===1&&item.active===false">
                {{item.id}}.<label v-bind:class="{changeCheckbox:item.active}">
                <input type="checkbox" v-model="item.active"/>{{item.name}}
            </label>
            </div>
            <div v-else-if="status===2&&item.active===true">
                {{item.id}}.<label v-bind:class="{changeCheckbox:item.active}">
                <input type="checkbox" v-model="item.active"/>{{item.name}}
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
            }

        }
    }

</script>

<style scoped>
    @import '../common.css';
</style>
