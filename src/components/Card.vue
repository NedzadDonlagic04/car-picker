<script>
    import Image from './Image.vue';
    import Info from './Info.vue';

    export default {
        components: { Image, Info },
        data() {
            return {
                image: undefined
            };
        }
    };
</script>

<template>
    <div class="card">
        <Image :show="image" />
        <Info />
    </div>
</template>

<style scoped>
    .card {
        --shadow-color: hsl(0, 10%, 30%);

        border: 3px solid black;
        border-radius: 5px;
        box-shadow: -10px -10px 15px var(--shadow-color);
        height: 600px;
        width: 500px;
    }
</style>