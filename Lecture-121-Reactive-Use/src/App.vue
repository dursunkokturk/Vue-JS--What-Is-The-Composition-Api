<template>
    <h1>
        Ad: {{ myObject.firstName }}
    </h1>
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
            const handleClick = () =>{
                myObject.value.firstName="Dursun Köktürk"
            }

            const handleClickTwo = () =>{
                myObjectTwo.firstName="Dursun Köktürk"
            }
            return {myObject,myObjectTwo,name,age,handleClick,handleClickTwo}
        },
    }
</script>