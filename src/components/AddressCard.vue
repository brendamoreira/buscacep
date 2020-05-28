<template>
    <div>
        <p>Logradouro: <span>{{address.logradouro}}</span></p>
        <p>CEP: <span>{{address.cep}}</span></p>
        <p>Bairro: <span>{{address.bairro}}</span></p>
        <p>Localidade: <span>{{address.localidade}}/{{address.uf}}</span></p>
    </div>
</template>
<script>
export default {
    props: ['address']
    
}
</script>
<style scoped>
div {
    width: 300px;
    height: auto;
    border: 2px solid black;
    margin: auto;
    box-sizing: border-box;
}
p {
    margin: 0;
    padding: 5px 10px;
}
span{
    font-family: 'Courier New', Courier, monospace;
    font-size: 0.8rem;
    color: rgb(94, 94, 94);
}
</style>