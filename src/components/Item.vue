<template>
    <div>
        <p v-for="item in items">
            <label><input type="checkbox"/>{{item.name}}</label>
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
        }
    }

</script>

<style scoped>

</style>
