<template>
    <div>
        <div class="modal" :class="activate">
            <div class="modal-background"></div>
            <div class="modal-card is-primary">
                <header class="modal-card-head">
                <p class="modal-card-title">Kontakt</p>
                <button class="delete" aria-label="close" @click='close'></button>
                </header>
                <section class="modal-card-body">
                <h1>Hej</h1>
                <img src="../img/waving-hand.png">
                <p>Vad kan vi hjälpa dig med? Skriv ett meddelande så kontaktar vi dig. Önskas en offert vänligen bifoga antal anställda samt fakturor per månad.</p>
                <form id="gform" form="form" method="POST" action="http://formspree.io/hej@lr-orebro.se">
                    <div class="control has-icons-left has-icons-right">
                        <p :class="{ 'control': true }">
                            <input v-validate="'required|email'" :class="{'input': true, 'is-danger': errors.has('email') }" name="email" type="text" placeholder="Email">
                            <span v-show="errors.has('email')" class="help is-danger">{{ errors.first('email') }}</span>
                        </p>
                    <span class="icon is-left">
                        <i class="fa fa-envelope"></i>
                    </span>
                    <span class="icon is-right">
                        <i class="fa fa-check"></i>
                    </span>
                    </div>
                    <div class="values">
                    <div class="field is-grouped is-expanded">
                        <div class="control">
                            <label class="label">Årsomsättning (mKr):</label>
                            <input class="input valueOne" type="number" name="Omsattning" v-model="valueOne">
                        </div>
                        <div class="control">
                            <label class="label">Anställda:</label>
                            <input class="input valueTwo" type="number" name="Anstallda" v-model="valueTwo">
                        </div>
                        <div class="control">
                            <label class="label">Organisationsnummer:</label>
                            <input class="input valueTwo" name="Organisationsnummer" type="number">
                        </div>
                    </div>
                    </div>
                    <textarea class="textarea" name="Meddelande" placeholder="Meddelande">
                    </textarea>
                </form>
                </section>
                <footer class="modal-card-foot">
                <button form="gform" value="send" type="submit" class="button is-primary is-outlined">Skicka</button>
                <button class="button is-danger is-outlined" @click='close'>Cancel</button>
                </footer>
            </div>
        </div>
    </div>
</template>

<script>

export default {
  name: 'contactModal',
  props: ['activate', 'valueOne', 'valueTwo'],
  methods: {
    close () {
      this.$emit('closeRequest')
    }
  }
}
</script>

<style scoped lang="scss">
    @import '../style/main.scss';
    h1 {
        display:inline; 
    }
    img {
        max-width:10%; 
        margin-left:20px; 
    }
    header.modal-card-head {
        background-color:$green; 
    }
    form {
        margin-top:20px; 
    }
    .modal {
        min-height:100%; 
        z-index:9999999999; 
    }
    .modal-card {
        max-width: 100%;
        max-height: 100%;
    }
    .values {
        .control {
            margin-top:20px; 
        }
        .valueOne, .valueTwo, {
            width:100%; 
        }
    }
    .textarea {
        margin-top:20px;
    }
    input:valid > div.control.has-icons-left.has-icons-right > span.icon.is-right > i {
        background-color:green; 
    }
    .is-grouped {
        -ms-flex-wrap:wrap;
            flex-wrap:wrap; 
    }
    @media screen and (min-width: 779px){ 
        .modal.is-active { 
            display: -webkit-box; 
            display: -ms-flexbox; 
            display: inline-block; 
        } 
        .modal-card { 
            /* margin-top: 1px;  */
        } 
    }
</style>
