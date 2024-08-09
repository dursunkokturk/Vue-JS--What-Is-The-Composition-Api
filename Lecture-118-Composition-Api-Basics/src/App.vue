<template>
    <h1>
        Ad: {{ firstName }}
    </h1>  
    <h2>
        Yaş {{ age }}
    </h2>
    <button @click="handleClick">
        Tıkla
    </button>
</template>

<script>
    export default {
        name: 'App',
        setup(){
            let firstName ='Dursun';
            let age=32;
            const handleClick = () =>{
                console.log('Cliked')
            }
            return {firstName,age,handleClick}
        },
    }
</script>