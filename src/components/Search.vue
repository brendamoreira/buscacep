<template>
    <div>
        <form @submit.prevent="searchCep">
            <input type="text" v-model="cep" placeholder="Digite o CEP">
            <button type="submit"><i class="fa fa-search"></i></button>
        </form>
    </div>
</template>
<script>
export default {
    name:'Search',
    data() {
        return{
            cep: '',
        }
    },
    methods: {
        searchCep(){
            if(this.cep.trim() !== ''){
                this.$emit('search',this.cep);
                this.cep= '';
            }
        }
    }
}
</script>
<style scoped>
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css');

* {
  box-sizing: border-box;
}
input[type=text] {
    width: 80%;
    padding: 10px;
    font-size: 17px;
    border-style: none;
    border-radius: 3px 0 0 3px;
    background: white;
}

button {
    width: 20%;
    padding: 10px;
    background: #00afc1;
    color: white;
    font-size: 17px;
    border-style: none;
    border-left: none;
    cursor: pointer;
    border-radius: 0 3px 3px 0;
}

form button:hover {
    background: #0b7dda;
}

form{
    width: 300px;
    height: auto;
    margin: auto;
    border: 1px solid rgb(119, 142, 155);
    border-radius: 4px;
    display: flex;
}
div {
    margin: 0;
    padding: 40px;
}
</style>