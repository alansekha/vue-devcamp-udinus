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
import { ref, onBeforeUnmount, onUnmounted, watch } from 'vue';

export default {
    props: {
        items: {type: Array, default: []}
    },  
    setup(props, {emit}) {
        const count = ref(0)

        const increaseCount = () => {
            count.value++
            emit('increaseCount', count.value)
        }

        onBeforeUnmount(() => {
            console.log('beforeUnmount')
        })

        onUnmounted(() => {
            console.log('unmounted')
        })

        watch(() => props.items, (newValue, oldValue) => {
            alert('items changed')
        }, {deep:true});

        return {
            count,
            increaseCount
        };
    }
};
</script>

