<template>
  <div>helllo {{ datasensor }} {{ datasensor2 }}
  <button @click="getData" class="bg-orange-500 p-2 rounded-xl">Ambil Data</button> &nbsp;
  <button @click="getData" class="bg-orange-500 p-2 rounded-xl">Ambil Data 2</button>
  </div>
</template>

<script> //tempat ngoding java script
export default {
  data(){
    return{
      datasensor : "60",
      datasensor2 : "80"
    }
  },
  created(){
    //this.getData()
   // this.getData1()
  },
  methods: {
    //getData1(){
    //  alert('hello')
   // },
    async getData(){
      const data = await fetch("http://localhost:3000/datasensor1")
      const datajson = await data.json()
      console.log(datajson)
      this.datasensor = datajson.sensor3
    
      
      }

  },

}
</script>

<style>

</style>