<template>
    <div>
        <!-- Header  -->
        <lr-menu></lr-menu>
        <!-- Banner  -->
        <div class="contactImage overlay">
            <div class="quote container">
                <h3 class="responsiveHeading">Håll koll på din ekonomi i mobilen <br /> med Lr-Online</h3>
            </div>
        </div>
        <div class="section container lrOnlineText">
            <p class="mainText">
                Med denna rapportering förvandlar vi er bokföringsdata till enkla visuella rapporter. Genom LR-Online har du tillgång till ditt företags ekonomi när du vill och var du vill. Du får snabbt en övergripande bild över din verksamhet men kan även analysera på detaljnivå och följa dina kostnader och intäkter dag för dag. Du får även med ett dokumentarkiv där rapporteringen sparas för varje månad, men även möjlighet att själv lagra viktiga dokument och avtal på ett säkert sätt. 
            </p>
        </div>
        <!-- Content on page LR online -->
        <div class="section flex">
            <div class="card">
                <div class="card-content">
                        <div class="cardImage">
                            <img src="../img/lr-online.png" alt="lr-online">
                        </div>
                    <strong>Som kund hos oss får du din ekonomiska rapportering via LR-Online.</strong> 
                </div>
            </div> 
            <div class="card">
                <div class="card-content">
                <p class="title">Logga in på Lr-Online</p>
                <!-- target blank to get the inlogged page to show in a new tab -->
                <!-- form to log in to LR online -->
                <form action="https://monitor.foretagsplatsen.se/Login" method="post" target="_blank"> 
                    <input type="hidden" id="theme" name="theme" value="KundId" />     
                    <input type="hidden" id="cultureInfo" name="cultureInfo" value="sv-SE" />   
                    <p>
                        <label for="username">Användare:</label>  
                        <input class="input" type="text" id="username" name="username">
                    </p>
                    <p>
                        <label for="password">Lösenord:</label>  
                        <input class="input" type="password" id="password" name="password">   
                    </p>  
                    <button class="button is-primary is-outlined" type="submit" value="Logga in">Logga in</button>  
                </form>  
                </div>
            </div>
        </div>
        <!-- Footer here -->
        <lrFooter></lrFooter>
    </div>
</template>

<script>
import lrMenu from '@/components/lrMenu.vue'
import lrFooter from '@/components/lrFooter.vue'
export default {
  name: 'lrOnline',
  components: {
    lrMenu,
    lrFooter
  }
}
</script>

<style scoped lang="scss">
    @import '../style/main.scss';
    /* styling for quote inside header */
    .quote {
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -webkit-box-align: center;
            -ms-flex-align: center;
                align-items: center;
        -webkit-box-pack: center;
            -ms-flex-pack: center;
                justify-content: center;
        -webkit-box-orient: vertical;
        -webkit-box-direction: normal;
            -ms-flex-direction: column;
                flex-direction: column;
        height: 100%;
        text-align: center;
        h3 {
            color:$white; 
            z-index:450; 
            width:80%; 
            font-size:35px; 
        }
        span {
            font-size: 40px;
            font-weight: bold;
            z-index: 1000;
        }
        .quoteTextContact {
            z-index: 300;
            margin-top: 0;
            margin-bottom:0;
            text-align: center;
            width: 90%;
        }
        .fa {
            font-size: 40px;
            padding-right: 20px;
        }
    }
    .lrHeaderLine {
        background-color: $red;
    }
    .contactImage {
        margin-top:67px; 
        background-image: url("../img/lrContact.jpeg"); 
        background-repeat: no-repeat; 
        background-position:center; 
        background-size:cover; 
        width:100%; 
        height:250px; 
        position:relative; 
    }
    .flex {
        height:100%; 
        padding-bottom: 20px;
        display:-webkit-box; 
        display:-ms-flexbox; 
        display:flex;
        align-items: stretch;
        -webkit-box-align: stretch;        
        -ms-flex-align: stretch;        
        align-items: stretch;
        -webkit-box-orient:horizontal;
        -webkit-box-direction:normal;
            -ms-flex-direction:row;
                flex-direction:row;  
        -webkit-box-pack:center;  
            -ms-flex-pack:center;  
                justify-content:center; 
    }
    .card { 
        width:50%;
    }
    .card-content {
        display:-webkit-box;
        display:-ms-flexbox;
        display:flex; 
        -webkit-box-pack:center; 
            -ms-flex-pack:center; 
                justify-content:center; 
        -webkit-box-orient:vertical; 
        -webkit-box-direction:normal; 
            -ms-flex-direction:column; 
                flex-direction:column; 
        .cardImage {
            height: auto;
            text-align: center;
        }
    }
    button, p  {
        margin-top:30px; 
    }
    .lrOnlineText {
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -webkit-box-orient: vertical;
        -webkit-box-direction: normal;
        -ms-flex-direction: column;
                flex-direction: column;
        -webkit-box-pack: center;
        -ms-flex-pack: center;
                justify-content: center;
        -webkit-box-align: center;
        -ms-flex-align: center;
                align-items: center;
        padding-top: 0;
        padding-bottom:0; 
    }
    /* ****************** MEDIAQUERIES ****************** */
    @media screen and (max-width: $tablet - 1px) {
        .flex {
            -webkit-box-orient:vertical;
            -webkit-box-direction:normal;
                -ms-flex-direction:column;
                    flex-direction:column; 
        }
        .card {
            width:100%;
            height:auto;
        }
    }
</style>
