<template>
    <div>
        <h1>Conditional Rendering</h1>

        <div v-if="isDeadlineToday">
            Deadline hari ini
        </div>

        <div v-else-if="!isTaskCompleted">
            Tugas belum selesai
        </div>

        <div v-else>
            Tugas sudah selesai
        </div>
    </div>
</template>

<script>
export default {
    name: 'ConditionalRendering',
    data() {
        return {
            deadline: '2/6/2023',
            hariIni: new Date().toLocaleDateString('id-ID'),
            selesai: false
        }
    },
    computed: {
        isDeadlineToday() {
            return this.deadline === this.hariIni;
        },
        isTaskCompleted() {
            return this.selesai;
        }
    }
}
</script>

