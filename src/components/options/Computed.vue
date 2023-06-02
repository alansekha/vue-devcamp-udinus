<template>
    <div>
        <h1>Computed</h1>

        <!-- Computed Example -->
        <div>Total Marks: {{ totalMarks }}</div>
        <input type="number" v-model="number">
    </div>
</template>

<script>
export default {
    name: 'Computed',
    data() {
       return {
            number: 4
        }
    },
    methods: {
        totalMarkMethods() {
            return this.number * 2;
        }
    },
    computed: {
        totalMarks() {
            return this.number * 2;
        }
    }
}
</script>

