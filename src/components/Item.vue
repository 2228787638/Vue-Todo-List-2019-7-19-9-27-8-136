<template>
    <div>
        <p v-for="item in items">
            {{item.id}}.<label @change="clickMe(item.id)" v-bind:class="{changeCheckbox:item.active}">
                <input type="checkbox" v-model="item.active"/>{{item.name}}
            </label>
        </p>

    </div>
</template>

<script>
    /* eslint-disable vue/no-shared-component-data,no-unused-vars,no-console,no-undef */
    import global from '../common.vue';
    export default {
        name: "Item",
        data(){
            return {
                items:global.items
            }
        },
        methods: {
            clickMe(id) {
                alert(global.items[id-1].active);
            }

        }
    }

</script>

<style scoped>
    @import '../common.css';
</style>
