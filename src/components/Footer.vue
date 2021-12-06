<template>
  <div class="container">
        <div class="social-container">
            <ul>
                <li>
                    <i class="fab fa-facebook-f"></i>
                </li>
                <li>
                    <i class="fab fa-instagram"></i>
                </li>
                <li>
                    <i class="fab fa-twitter"></i>
                </li>
                <li>
                    <i class="fab fa-youtube"></i>
                </li>
            </ul>
         </div>
         <div class="linksF-ctn">
            <ul class="links-footer">
                <li v-for="(elFooter, i ) in footerLinks1" :key=" `el-${i}`">
                    <a href="/">
                    {{elFooter}}
                    </a>
                </li>
            </ul>

            <ul class="links-footer">
                <li v-for="(elFooter, i ) in footerLinks2" :key=" `el-${i}`">
                    <a href="/">
                    {{elFooter}}
                    </a>
                </li>
            </ul>

            <ul class="links-footer">
                <li v-for="(elFooter, i ) in footerLinks3" :key=" `el-${i}`">
                    <a href="/">
                    {{elFooter}}
                    </a>
                </li>
            </ul>

            <ul class="links-footer">
                <li v-for="(elFooter, i ) in footerLinks4" :key=" `el-${i}`">
                    <a href="/">
                    {{elFooter}}
                    </a>
                </li>
            </ul>

         </div>
  </div>
</template>

<script>
export default {
name: 'Footer',
data(){
    return{
        footerLinks1: [
            'Audio e sottotitoli',
            'Media Center',
            'Privacy',
            'Contattaci',
        ],
        footerLinks2: [
            'Audiodescrizione',
            'Rapporti con gli investitori',
            'Note legali',
        ],

        footerLinks3: [
            'Centro assistenza',
            'Opportunitá di lavoro',
            'Preferenze per i cookie',
        ],

        footerLinks4: [
            'Carta regalo',
            'Condizioni di utilizzo',
            "Informazioni sull'azienda",
        ],
    }
}

}
</script>

<style lang="scss" scoped>
    .container{
        width: 80%;
        margin: 20px auto;
        .social-container{
            width: 100%;
            ul{
                display: flex;
                list-style: none;
                li{
                    padding: 0 10px;
                    i{
                        font-size: 23px;
                    }
                }
            }
        }
        .linksF-ctn{
            display: flex;
            justify-content: space-between;
            margin: 15px 0;
            .links-footer{
                display: flex;
                list-style: none;
                flex-direction: column;
                li{
                    padding: 10px 10px;
                    a{
                        color: #fff;
                        text-decoration: none;
                        font-size: 13px;
                        &:hover{
                            text-decoration: underline;
                        }
                    }
                }
            }
        }
    }
</style>