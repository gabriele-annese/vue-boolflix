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
         <div class="btn-ctn">
                <button class="btn-footer">
                    Codice di servizio
                </button>
         </div>
         <div class="copyright">
             <span>
                 © 1997-2021 Gabflix, Inc.
             </span>
             <span>
                 {0f910b26-dc58-4745-b8c0-972088facc41}
             </span>
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
        width: 980px;
        margin: 50px auto;
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
                        color: grey;
                        text-decoration: none;
                        font-size: 13px;
                        &:hover{
                            text-decoration: underline;
                        }
                    }
                }
            }
        }
        .btn-ctn{
            width: 100%;
            .btn-footer{
                padding: 6px 5px;
                color: grey;
                background-color: transparent;
                border: 1px solid grey;
                &:hover{
                    cursor: pointer;
                    color: #fff;
                }
            }
        }
        .copyright{
            margin: 1.5rem 0;
            span{
                font-size: 13px;
            }
        }
    }
</style>