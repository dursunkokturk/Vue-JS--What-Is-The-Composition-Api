<template>
    <h1>
        Ad: {{ myObject.firstName }}
    </h1>

    <!-- ref Attribute Kullanilarak 
          Objenin Icindeki Attribute lara Ulasiyoruz -->
    <h2 ref="myRef">
        Yaş {{ myObject.age }}
    </h2>
    <h3>
        {{ lastName }}
    </h3>
    <button @click="handleClick">
        Handle Click
    </button>
    <h3>
        Reactive
    </h3>
    <h1>
        {{myObjectTwo.firstName}} - {{ myObjectTwo.age }}
    </h1> 
    <button @click="handleClickTwo">
        Handle Click Two
    </button>
</template>

<script>

    /* ref Kullanma Amaci 
        Obje Icindeki HTML Elementi Icinde 
        Data Yazdirma Isleminin Anlik Olarak Yapilmasini Saglar */
    /* ref Kullaniminda Obje Icine Data Yazdirmak Icin 
        Objenin Bulundugu Attribute u Attribute Yolunu Izleyerek 
        Tam Olarak Bulmak Gerekiyor */
    /* ref Kullanildiginda 
        Obje Icindeki Deger Sonradan Degistirilebilir */
    /* reactive Kullanma Amaci 
        Obje Icindeki HTML Elementi Icinde 
        Data Yazdirma Islemi Icin 
        Degisken Adindan Sonra Direkt En Sondaki Attribute Kullanilarak 
        Yazdirma Islemi Yapilabilir */
    /* reactive Kullanildiginda 
        Obje Icindeki Deger Sonradan Degistirilemez */
    import {ref,reactive} from 'vue'

    export default {
        name: 'App',
        setup(){
            const myObject = ref({
                firstName:'Dursun',
                age:31
            })
            const myObjectTwo = reactive({
                firstName:'Hakan',
                age:35
            })
            const name = ref('Dursun');
            const age = ref(32);

            /* ref Kullanarak Obje Icine Data Yazdirma Islemi */
            const handleClick = () =>{
                myObject.value.firstName="Dursun Köktürk"
            }

            /* reactive Kullanarak Obje Icine Data Yazdirma Islemi */
            const handleClickTwo = () =>{
                myObjectTwo.firstName="Dursun Köktürk"
            }
            return {myObject,myObjectTwo,name,age,handleClick,handleClickTwo}
        },
    }
</script>