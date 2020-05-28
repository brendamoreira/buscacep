<template>
    <div>
        <form class="search" style="margin:auto;max-width:300px" @submit.prevent="searchCep">
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
form.search input[type=text] {
  padding: 10px;
  font-size: 17px;
  border-style: none;
  border-radius: 3px;
  float: left;
  width: 80%;
  background: white;
}

form.search button {
  float: left;
  width: 20%;
  padding: 10px;
  background: #2196F3;
  color: white;
  font-size: 17px;
  border-style: none;
  border-left: none;
  cursor: pointer;
  border-radius: 0 3px 3px 0;
}

form.search button:hover {
  background: #0b7dda;
}

form.search::after {
  content: "";
  clear: both;
  display: table;
}
form{
    border: 1px solid grey;
    border-radius: 4px;
}
</style>