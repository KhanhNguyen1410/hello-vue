<template>
  <div class="hello">
    <div v-show="isShow">
      <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSaNGlEMBmyMD6uXamHaxzdyoPcwTPybEkobg&usqp=CAU" alt="Oke bro">
    </div>
    <div>
      <input :class= "{input : inputed}" type="text" :disabled = "disable">
      <input type="text" v-model="newModel"><br>
        <button @click="models.push({name : newModel , gender : 'M'  })">add name</button>
      <div v-for="(model, index) in models" :key="index">
        <table>
          <tr>{{model.name}}</tr>
          <tr>{{model.gender}}</tr>
        </table>
      </div>
      <input type="text" v-model="models[0].name">
      <button @click="disable = ! disable ">Iron man</button>  
      <button @mouseover="models[0].name = 'Nobi Stark'">click man</button>  

    </div>
<button @click="isShow = ! isShow">Iron man</button>  
</div>
</template>

<script>
export default {
  name: 'Menu',
  props: {
    msg: String
  },
  data() {
    return {
      isShow : true,
      disable : true,
      inputed : true,
      isMale: false,
      newModel : '',
      models : [
        {
          name : 'khanh',
          gender : 'M' 
        },
         {
          name : 'Huyen',
          gender : 'FE' 
        }
      ]
    }   
    },
    methods : {
      addModel : function(){
        
        this.models.push({
          name : this.newModel,

        })
      }
  }
}
</script>

<style scoped>
.input {
color: red;
}
</style>
