<template>
    <div class="container-loader">
        <h2>In attesa...</h2>

    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.container-loader{
    display: flex;
    align-items: center;
    justify-content: center;
    h2{
        margin: 50px 0;
        letter-spacing: 3px;
        text-transform: uppercase;
        animation: pulse 1s infinite alternate;
    }

    @keyframes pulse {
        from{
            transform: scale(1);
            color: #000
        }
        to{
            transform: scale(1.4);
            color: #e63946
        }
    }
}
</style>