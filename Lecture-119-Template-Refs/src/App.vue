<template>
    <h1>
        Ad: {{ firstName }}
    </h1>
    
    <!-- ref Attribute Kullanilarak 
          Objenin Icindeki Attribute lara Ulasiyoruz -->
    <h2 ref="myRef">
        Yaş {{ age }}
    </h2>
    <button @click="handleClick">
        Tıkla
    </button>
</template>

<script>
  import {ref} from 'vue'

  export default {
      name: 'App',
      setup(){
          let firstName ='Dursun';
          let age=32;

          /* ref Attribute unu 
              myRef Degiskeni Uzerinden Yonetiyoruz */
          const myRef= ref(null)
          const handleClick = () =>{

              /* myref.value Attribute Kullanilarak 
                  Obje Icindeki HTML Elementine Ulasiyoruz */
              console.log(myRef,myRef.value)

              /* myref.value Attribute Kullanilarak 
                  ref Attribute Bulunan HTML Elementinde
                  Obje Icindeki HTML Elementine Class Attribute Ekliyoruz
                  Ekledigimiz Class Attribute una Deger Veriyoruz */
              myRef.value.classList.add('Dursun');

              /* myref.value Attribute Kullanilarak 
                  ref Attribute Bulunan HTML Elementinde
                  Obje Icindeki HTML Elementine Yazi Yazdiriyoruz */
              myRef.value.textContent='Dursun Köktürk'
          }
          return {firstName,age,handleClick,myRef}
      },
  }
</script>