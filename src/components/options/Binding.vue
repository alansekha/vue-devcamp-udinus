<template>
    <div>
        <h1>Binding</h1>

        <!-- v-bind -->
        <div v-bind:id="id">Here I'am</div>

        <!-- v-bind alternative -->
        <div :id="id">I'm here !!</div>

        <!-- Two way binding -->
        <div>{{ 'Input :' + input }}</div>
        <input type="text" v-model="input" :placeholder="inputPlaceholder">

        <!-- Binding Class and Style -->
        <input type="number" v-model="padding" :placeholder="inputPlaceholder" :style="{ padding: padding + 'px' }">
        <div :class="{error: hasError, success: !hasError}"> Yahaha</div>
    </div>
</template>

<style>
    .error{
        padding: 10px;
        border: 1px solid red;
    }
    .success{
        padding: 10px;
        border: 1px solid green;
    }
</style>
<script>
export default {
    name: 'Binding',
    data() {
       return {
            id: 'yahaha',
            input: '',
            inputPlaceholder: 'Masukkan Input',
            padding: 0,
            hasError: false
        }
    }
}
</script>

