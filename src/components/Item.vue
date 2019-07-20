<template>
    <div>
        <p v-for="item in items">
            <label><input type="checkbox"/>{{item.name}}</label>
        </p>

    </div>
</template>

<script>
    /* eslint-disable vue/no-shared-component-data,no-unused-vars,no-console,no-undef */
    import Bus from '../bus';
    export default {
        name: "Item",
        data(){
            return {
                items:[
                    {
                        name: 1,
                        active: true
                    },
                    {
                        name: 2,
                        active: true
                    },
                    {
                        name: 3,
                        active: true
                    }
                ]
            }
        }
    }

</script>

<style scoped>

</style>
