<template>
    <div class="Billboard">
        <div class="innerBillboard">
            <img class="heroimg" src="../assets/heroGabflix.jpg" alt="">
            <div class="titleHero">
                <img  src="../assets/heroTitle.png" alt="">
                <div class="paragraph">
                    <p>
                        Un allevatore autoritario ma carismatico tormenta la nuova moglie del fratello e il figlio di lei, fino a quando non vengono a galla segreti nascosti da troppo tempo.
                    </p>
                </div>
                <div class="btn-hero">
                    <a href="/"> 
                    <span>
                        <i class="fas fa-play"></i>
                    </span>
                    Play </a>
                    <button>
                        <i class="fas fa-info-circle"></i>
                        <span>
                            More Info
                        </span>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
name: 'Billboard'
}
</script>
<style lang="scss" scoped>
    .Billboard{
        position: relative;
        width: 100%;
        height: 56.25vw;
        z-index: 1;
        .innerBillboard{
            position: absolute;
            z-index: -1;
            width: 100%;
            height: 100%;
            .heroimg{
                width: 100%;
                height: 100%;
            }
            .titleHero{
            position: absolute;
            top: 0;
            bottom: 35%;
            left: 4%;
            width: 40%;
            z-index: 10;
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            .btn-hero{
                display: flex;
                margin-top:  1rem;
            }
            .btn-hero a,
            .btn-hero button {
                background-color: #ffff;
                border-radius: 4px;
                border: none;
                padding: 0.5rem 1.1rem;
                display: flex;
                align-items: center;
                font-weight: bold;
                margin-right: 0.5rem;
                cursor: pointer;
            }
            .btn-hero a{
                text-decoration: none;
                color: #000;
            }
            .btn-hero span,
            .btn-hero button span{
                margin-left: 0.5rem;
                margin-right:  1rem;
            }

            .btn-hero button{
                color: #fff;
                background-color: rgba(109, 109, 110, 0.7);
            }

            .btn-hero i{
                font-size: 15px;
            }
            .btn-hero .fa-info-circle{
                font-size: 20px;
            }
            .paragraph{
                width: 80%;
                margin-top: 0.5rem;
                font-size: 1.2rem;
            }
        }
        }
    }
</style>