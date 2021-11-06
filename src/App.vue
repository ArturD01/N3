<template>
  <div class="wrapper">

    <div class="wrapper-content">
  <div class="conteiner">

    <button class="btn btnPrimary" @click="modalFirst = !modalFirst">Show first modal</button>
     <modals
      title="First modal"
      v-show="modalFirst"
      @close="modalFirst= false">
      
      <div slot="body">
        <p>Text</p>
        <button class="btn btnPrimary" @click="modalFirst = !modalFirst">Well done</button>
      </div>
      
      </modals>

<button class="btn btnPrimary" @click="modalSecond.show = !modalSecond.show">Show second modal</button>
     <modals
      title="Modal with form"
      v-show="modalSecond.show"
      @close="modalSecond.show= false">
      
      <div slot="body">
        <form @sabmit.prevent="submitSecondForm">
          <label>Name:</label>
          <input type="text" required v-model="modalSecond.name">
          <label>Email:</label>
          <input type="email" required v-model="modalSecond.email">
        <button class="btn btnPrimary">Subnit</button>
        </form>
      </div>
        
      </modals>

  </div>
    </div>

  </div>
  
</template>

<script>
import modals from '@/components/Modal.vue'
export default {
 components: {modals},
 data () {
   return {
     modalFirst: false,
     modalSecond:{
       show: false,
       name:'',
       email:'',
     }
   }
 },
 methods:{
   submitSecondFor (){
     console.log({
       name: this.modalSecond.name,
       email: this.modalSecond.email
     })
     this.modalSecond.name=""
     this.modalSecond.email=""
     this.modalSecond.show=false
   }
 }
}
</script>

<style>

</style>
