<template>
    <h1>
        Ad: {{ firstName }}
    </h1>
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

            const myRef= ref(null)
            const handleClick = () =>{
                console.log(myRef,myRef.value)
                myRef.value.classList.add('Dursun');
                myRef.value.textContent='Dursun Köktürk'
            }
            return {firstName,age,handleClick,myRef}
        },
    }
</script>