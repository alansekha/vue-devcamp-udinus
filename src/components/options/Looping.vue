<template>
    <div>
        <h1>Looping</h1>

        <!-- Cara ke 1 -->
        <ul>
            <li v-for="item in items" :key="item.id">{{ item.name }}</li>
        </ul>

        <!-- Cara ke 2 -->
        <ul>
          <li v-for="(item, index) in items" :key="index">{{ item.name }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Looping',
    data() {
       return {
            items: [
                { id: 1, name: 'Item 1' },
                { id: 2, name: 'Item 2' },
                { id: 3, name: 'Item 3' }
            ]
        }
    }
}
</script>

