<template>
    <h1>
        Ad: {{ firstName }}
    </h1>

    <!-- ref Attribute Kullanilarak 
          Objenin Icindeki Attribute lara Ulasiyoruz -->
    <h2 ref="myRef">
        Yaş {{ age }}
    </h2>
    <h3>
        {{ lastName }}
    </h3>
    <button @click="handleClick">
        Tıkla
    </button>
    <button @click="handleClickOption">
        Tıkla
    </button>
</template>

<script>

    /* ref Kullanma Amaci 
        Obje Icindeki HTML Elementi Icinde 
        Data Yazdirma Isleminin Anlik Olarak Yapilmasini Saglar v*/
    import {ref} from 'vue'

    export default {
        name: 'App',
        setup(){
            const firstName = ref('Dursun');
            const age = ref(32);

            /* ref Attribute unu 
                myRef Degiskeni Uzerinden Yonetiyoruz */
            //  const myRef= ref(null)

            const handleClick = () =>{
                firstName.value="Dursun Köktürk";
                age.value=33;

                /* myref.value Attribute Kullanilarak 
                  Obje Icindeki HTML Elementine Ulasiyoruz */
                // console.log(myRef,myRef.value)

                // name='Dursun Köktürk'

                /* myref.value Attribute Kullanilarak 
                  ref Attribute Bulunan HTML Elementinde
                  Obje Icindeki HTML Elementine Class Attribute Ekliyoruz
                  Ekledigimiz Class Attribute una Deger Veriyoruz */
                // myRef.value.classList.add('Dursun');

                /* myref.value Attribute Kullanilarak 
                  ref Attribute Bulunan HTML Elementinde
                  Obje Icindeki HTML Elementine Yazi Yazdiriyoruz */
                // myRef.value.textContent='Dursun Köktürk'
            }
            return {firstName,age,handleClick}
        },
        data() {
            return {
                lastName:'Köktürk'
            }
        },
        methods: {
            handleClickOption(){
                this.lastName="Dursun Köktürk"
            }
        },
    }
</script>