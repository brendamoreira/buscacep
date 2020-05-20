<template>
    <div>
        <form class="search" style="margin:auto;max-width:300px">
            <input type="text" placeholder="Digite o CEP">
            <button type="submit"><i class="fa fa-search"></i></button>
        </form>
    </div>
</template>
<script>
export default {
    name:'Search',
    
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
  border: 1px solid grey;
  border-radius: 3px;
  float: left;
  width: 80%;
  background: #f1f1f1;
}

form.search button {
  float: left;
  width: 20%;
  padding: 10px;
  background: #2196F3;
  color: white;
  font-size: 17px;
  border: 1px solid grey;
  border-left: none;
  cursor: pointer;
  border-radius: 3px;
}

form.search button:hover {
  background: #0b7dda;
}

form.search::after {
  content: "";
  clear: both;
  display: table;
}

</style>