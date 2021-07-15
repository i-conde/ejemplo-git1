<template>
  <div class="home">
    
    <h1
      :style="cambiaColor"
    > {{titulo}}: {{contador}} </h1>
    <hr>
    <BtnAccion2 :estado="true" :numero="50"  /> 
    <BtnAccion2 :estado="false" :numero="10"  /> 

    <!-- <button @click="accionAumentar">Aumentar/</button> -->
  </div>
</template>

<script>
import BtnAccion2 from '../components/BtnAccion2'
import { mapState, mapMutations, mapActions } from 'vuex'

export default {
  name: 'Home',
  components: {
    BtnAccion2
  },

  data() {
    return {
      titulo: 'Mi contador'
    }
  },

  computed:{
    ...mapState(['contador']),
    cambiaColor(){
      return [this.contador < 100 ? {'color':'red'} : {'color':'green'} ]
    }
  },

  methods:{
    //...mapMutations(['incrementar']),
    /* ...mapActions(['accionAumentar']) */
  }
}
</script>
