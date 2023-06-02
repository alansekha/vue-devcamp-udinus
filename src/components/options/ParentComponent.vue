<template>
    <div>
        <h1>Parent Child Component</h1>

        <!-- Parent Child Component -->
        <Child @increaseCount="increaseCount" />
        <div>Ini ada di parent component: {{ count }}</div>

        <!-- Slot to Child -->
        <Child> 
            Wahyu
        </Child>

        <!-- Lifecycle Test -->
        <Child @increaseCount="increaseCount" v-if="show" />
        <div>Ini ada di parent component: {{ count }}</div>
        <button @click="show = !show">Hidden Child</button>

        <!-- Watch Example -->
        <Child :items="items"/>
        <button @click="removeItems">Remove Items</button>
    </div>
</template>

<script>
import Child from './child/Child.vue'

export default {
    name: 'ParentComponent',
    components: {
        Child
    },
    data() {
        return {
            count: 0,
            show: true,
            items: [
                { id: 1, name: 'Item 1' },
                { id: 2, name: 'Item 2' },
                { id: 3, name: 'Item 3' }
            ]
        }
    },
    methods: {
        increaseCount(value) {
            this.count = value
        },
        removeItems() {
            this.items.splice(0,1);
        }
    },
    beforeMount() {
        console.log('beforeMount')
    },
    mounted() {
        console.log('Mounted')
    },
    beforeUpdate() {
        console.log('Before update')
    },
    updated() {
        console.log('Updated')
    }
}
</script>

