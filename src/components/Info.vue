<script>
    export default {
        methods: {
            selectMe(event) {

                this.$refs.ball1.classList.remove('selected');
                this.$refs.ball2.classList.remove('selected');
                this.$refs.ball3.classList.remove('selected');

                event.target.classList.add('selected');

                this.$emit('show', event.target.getAttribute('data-color'));
            },
            purchase(event) {
                if(event.target.innerText == 'Purchase made!')
                {
                    event.target.innerText = 'Buy'
                }
                else
                {
                    event.target.innerText = 'Purchase made!'
                }
            }
        }
    };
</script>

<template>
    <div class="info">
        <h1>Sedan, 2022 Kia Rio</h1>
        
        <div class="text">
            <p>Price: $19,881</p>
            <p>Distance: 440</p>
        </div>

        <div class="ball-box">
            <p>Pick the color:</p>
            <div ref="ball1" data-color="black" class="ball selected" @click="selectMe"></div>
            <div ref="ball2" data-color="gray" class="ball" @click="selectMe"></div>
            <div ref="ball3" data-color="red" class="ball" @click="selectMe"></div>
        </div>

        <button @click="purchase">Buy</button>
    </div>
</template>

<style scoped>
    .info {
        height: 50%;
        background-color: hsl(120, 80%, 40%);
        padding: 15px;
        display: grid;
        grid-template-rows: 1fr 1fr 2fr 1fr;
    }

    h1 {
        font-size: 2rem;
        text-align: center;
        place-self: center;
        color: white;
    }

    p {
        font-size: 1.5rem;
        margin-top: auto;
        color: white;
    }

    .ball-box p {
        margin-top: 20px;
    }

    .ball {
        display: inline-block;
        margin: 10px;
        height: 30px;
        width: 30px;
        border-radius: 50%;
        border: 2px solid white;
    }

    .ball:nth-child(2) {
        background-color: black;
    }
    
    .ball:nth-child(3) {
        background-color: hsl(0, 0%, 50%);
    }

    .ball:nth-child(4) {
        background-color: hsl(0, 100%, 60%);
    }

    .selected {
        border: 3px solid white;
        transform: scale(1.3);
    }

    .ball:hover,
    button:hover {
        cursor: pointer;
    }

    button {
        width: 30%;
        height: 60%;
        margin: 10px 0px 0px 5px;
        border-radius: 5px;
    }
</style>