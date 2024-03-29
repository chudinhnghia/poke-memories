<template>
    <div class="main">
        <header class="header">
            <h1>POKE MEMORIES</h1>
            <p>Select mode to start game</p>
        </header>
        
        <div class="content">
            <button v-on:click="gameMode(16)">
                <span class="content__size">4x4</span>
                <span class="content__regime">Easy</span>
            </button>
            <button v-on:click="gameMode(32)">
                <span class="content__size">6x6</span>
                <span class="content__regime">Normal</span>
            </button>
            <button v-on:click="gameMode(64)">
                <span class="content__size">8x8</span>
                <span class="content__regime">Hard</span>
            </button>
            <button v-on:click="gameMode(100)">
                <span class="content__size">10x10</span>
                <span class="content__regime">Super Hard</span>
            </button>
        </div>
    </div>
</template>

<script>
export default {
    methods: {
        gameMode(totalOfBlock) {
            this.$emit('gameMode', { totalOfBlock });
        }
    }
}
</script>

<style scoped lang="css">
    .main {
        text-align: center;
        height: 100vh;
        padding-top: 300px;
        background-color: var(--dark);
        color: var(--ligth);
    }

    .header h1 {
        font-size: 4.5rem;
    }

    .header p {
        font-size: 2rem;
    }

    .content {
        margin-top: 32px;
    }

    .content button {
        margin: 0 5px;
        width: 150px;
        height: 150px;
        background-color: var(--dark);
        border: 1px solid var(--ligth);
        border-radius: 0.9375rem;
        color: var(--ligth);
        font-family: var(--font);
        cursor: pointer;
        transition: background-color 0.3s ease-in-out;
    }

    .content button:hover {
        background-color: var(--ligth);
        color: var(--dark);
    }

    .content__size {
        font-size: 2rem;
        display: block;
    }

    .content__regime {
        font-size: 1.25rem;
    }
</style>