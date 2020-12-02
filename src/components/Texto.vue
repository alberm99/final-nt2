<template>
  <section class="src-components-estructura">
    <div>
      <div>
        <label for="color">Color</label>
        <input type="text" id="color" v-model="this.color">
      </div>

      <div>
        <label for="fondo">Fondo</label>
        <input type="text" id="fondo" v-model="this.fondo">
      </div>

      <div>
        <label for="tamaño">Tamaño</label>
        <input type="text" id="tamaño" v-model="this.size">
      </div>

      <hr>

      <div>
        <label for="texto">Texto</label>
        <input type="text" id="texto" :style="{'color': getColor(), 'background-color': getFondo(), 'font-size': getSize()} " v-model="this.texto">
      </div>


      <div v-if="cant>0">
        <p>Cantidad palabras: {{cant}}</p>
      </div>
    </div>

    <br>
    <br>
    <hr>
    <hr>


    <div>
      <h2>Choice</h2>

      <table>
        <tr>
          <th>Pregunta</th>
          <th>Respuesta</th>
        </tr>
        <tr v-for="(p, index) in preguntas" :key="index">
          <td>{{ p.pregunta }}</td>
          <td>{{ p.respuestas }}</td>
        </tr>
      </table>

    </div>


  </section>
</template>

<script>


  export default {
    name: "src-components-estructura",
    props: [],
    mounted() {
    
    },
    data() {
      return{
        color: '',
        fondo: '',
        size: '',
        texto: '',
        preguntas: [
          {pregunta: 1, respuestas: 'b' },
          {pregunta: 2, respuestas: 'c' },
          {pregunta: 3, respuestas: 'b' },
          {pregunta: 4, respuestas: 'c' },
          {pregunta: 5, respuestas: 'd' }
        ]
      
      }
    },
    methods: {
      getColor(){
        return this.color
      },
      getFondo(){
        return this.fondo
      },
      getSize(){
        return this.size
      },
      
    },
    computed: {
      cant(){
        let cant
        if(this.texto == ''){
          cant = 0
        }else{
          cant = this.texto.trim().split(' ').length 
        }
        return cant 
      }
    },
  };
</script>

<style scoped lang="css">
.src-components-estructura {
}


hr {
  background-color: #222;
  
}



label{
  color: #000;
  font-size: 25px;
  margin: 7px;
}

td {
  text-align: center;
  
}
</style>
