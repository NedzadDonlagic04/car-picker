<script>
    export default {
        props: {
            show: {
                type: String,
                default: 'black'
            }
        }
    };
</script>

<template>
    <div class="images">
        <img v-if="show === 'black'" src="./../assets/black-car.jpeg" alt="black-car">
        <img v-else-if="show === 'gray'" src="./../assets/gray-car.jpg" alt="gray-car">
        <img v-else src="./../assets/red-car.jpg" alt="red-car">
    </div>
</template>

<style scoped>
    .images {
        height: 40%;
        border-bottom: 2px solid black;
        display: flex;
        justify-content: center;
    }

    img {
        max-height: 100%;
    }
</style>