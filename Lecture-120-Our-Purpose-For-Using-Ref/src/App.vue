<template>
    <h1>
        Ad: {{ firstName }}
    </h1>
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
    import {ref} from 'vue'

    export default {
        name: 'App',
        setup(){
            const firstName = ref('Dursun');
            const age = ref(32);
            //  const myRef= ref(null)
            const handleClick = () =>{
                firstName.value="Dursun Köktürk";
                age.value=33;
                // console.log(myRef,myRef.value)
                // name='Dursun Köktürk'
                // myRef.value.classList.add('Dursun');
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