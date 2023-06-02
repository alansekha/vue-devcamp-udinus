<template>
    <div>
        <!-- Parent Child Example -->
        <button @click="increaseCount">Click Here</button>
        <div> Ini ada di Child Component: {{ count }}</div>

        <!-- Slot Example -->
        <div>
            Tambahan :
            <slot></slot>
        </div>

        <!-- Watch Effect -->
        <ul>
            <li v-for="item in items" :key="item.id">{{ item.name }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    props: {
        items: {type: Array, default: []}
    },  
    data() {
       return {
            count: 0
        }
    },
    methods: {
        increaseCount() {
            this.count++
            this.$emit('increaseCount', this.count)
        }
    },
    watch: {
        items: {
            handler(value, oldValue) {
                alert('items changed')
            },
            deep: true
        }
    },  
    beforeUnmount() {
        console.log('beforeUnmount')
    },
    onUnmounted() {
        console.log('unmounted')
    }
}
</script>

