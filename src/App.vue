<template>
  <div>
    <h1>{{ titulo }}</h1>
      <hr>
      <h2>{{ aula1 }}</h2>
      <p>Aula sobre instalação do Vue.Js</p>
      <p> exemplo simples do uso de duplas chaves {} para interpolação de dados.</p>
    <hr>

    <h2>{{ aula2 }}</h2>
      <p>Mensagem interpolada com duplas chaves, exemplo:' {{ mensagem }} '</p>
      <p>Expressão Javascript Multiplicação 2 x  3 = {{ 2 * 3 }}</p>
      <p>Expressão Javascript  soma de valores do Data valor1 = {{valor1}}, valor2 = {{ valor2 }}, resultado: {{ valor1 + valor2 }} </p>
      <p>Tamanho da mensagem 'Interpolação com Vue.js' com length: {{ mensagem.length }} caracteres</p>
      <p>Mensagem em Maiusculo: {{ mensagem.toUpperCase() }}</p>
      <hr>

    <h2>{{ aula3 }}</h2>
      <div v-show="detalhes">
        <p> v-show 'true' - Mensagem em Maiusculo: {{ mensagem.toUpperCase() }}</p>
      </div>
      <div v-if="detalhes">
        <p> v-if 'true' - Mensagem em Maiusculo: {{ mensagem.toUpperCase() }}</p>
        <p>Obs.: v-if não aparece na estrutura do DOM</p>
      </div>
      <hr>

      <h2>{{ aula4 }}</h2>
      <div v-if="detalhes1">
        <p> v-if 'true' - Mensagem em Maiusculo: {{ mensagem.toUpperCase() }}</p>
        <p>Obs.: v-if não aparece na estrutura do DOM</p>
      </div>
      <div v-else>Informações escondidas pelo v-if</div>
    <hr>

    <h2>{{ aula5 }}</h2>
        <div> 
          <ul>
            <li>methods são usados para guardar funções no componente</li>
            <li>Essas funções podem tratar dados e executar funcionalidades específicas.</li>
            <li>Os métodos definidos em methods podem ser chamados com argumentos.</li>
            <li>Eles não possuem cachê, o que significa que sempre são executados quando invocados.</li>
            <li>Ideal para lógica que não depende de valores reativos e precisa ser recalculada a cada chamada.</li>
          </ul>
        </div>
        <p>Exemplos:</p>
        <p> O uso do método boasVindas - {{ boasVindas() }}</p>
        <p> Uso do método verificarParouImpar - o valor 10 é {{  verificarParouImpar(10) }}</p>
        <p>outro exemplo - o valor {{ valor2 }} é {{ verificarParouImpar(valor2) }}</p>
      <hr>

    <h2>{{ aula6 }}</h2>
        <ul>
          <li>As computed properties são uma mistura de methods e data.</li>
          <li>Elas são funções que retornam dados e são reativas.</li>
          <li>O resultado é armazenado em cache e reexecutado apenas se alguma dependência (como o valor de uma variável) for alterada.</li>
          <li>Útil para cálculos complexos ou formatação de dados.</li>
          <li>Exemplo: se você precisa calcular estilos CSS com base em valores do componente, use computed23.</li>
        </ul>
      <p>Usando Computed </p>
      <p>Mensagem normal: {{ mensagem }}</p>
      <p>Mensagem Invertida: {{ mensagemInvertida }}</p>
      <p>Obs: </p>
      <ul>
        <li>Use methods para funções simples e que não dependem de valores reativos.</li>
        <li>Use computed para cálculos mais complexos e que precisam ser reavaliados apenas quando as dependências mudam.</li>
      </ul>
      <hr>

     <h2>{{ aula7 }}</h2> 
      <p>Exemplo: </p>
      <p> <button v-on:click="inverterMensagem">Inverter mensagem</button>   {{ mensagem }} </p> 
      <p><button @click="adicionar">Adicionar</button> Valor atual: {{ valor1 }} </p>
      <hr>

    <h2>{{ aula8 }}</h2>
      <p><button @click="adicionar2">Adicionar</button> Valor atual: {{ valor2 }}  <button @click="diminuir">Diminuir</button></p>
      <p><input type="text" @keyup="alterarMensagem">  Digitando: {{ mensagem2 }}</p>
    <hr>

    <h2>{{ aula9 }}</h2>
    
      <p><input v-bind:value="mensagem3" type="text" @keyup="alterarMensagem2">  Digitando: {{ mensagem3 }}</p>
      <p> Documentação Vue Js <a  target="_blank" :href="url">Link</a> </p>
      <button :disabled="disabled">Desabilitado</button><button :disabled2="disabled2">habilitado</button>
     <hr>

     <h2>{{ aula10 }}</h2>
     <p>É usado a diretiva  v-model para acessar os dados.</p>
     <p><input v-model="mensagem4" type="text" @keyup="alterarMensagem3">  Digitando: {{ mensagem4 }}</p>
    <hr>

    <h2>{{ aula11 }}</h2>
    <p>É usado a diretiva v-for</p>
    <p>Listagem</p>
    <ul>
      <li v-for="fruta in frutas" :key="fruta">{{ fruta }}</li>
    </ul>
    <hr>

    <h2>{{ aula12 }}</h2>
      <p>É usado a diretiva v-for para acessar o </p>
      <p>Listagem no formato de objeto</p>
      <ul>
        <li v-for="fruta1 in frutas2" :key="fruta1.nome">{{ fruta1.nome }}</li>
      </ul>
      
      <p>Listagem com indices</p>
      <ul>
        <li v-for="(fruta1, index) in frutas2" :key="fruta1.nome">{{index+1}} - {{ fruta1.nome }}</li>
      </ul>
    <hr>

    <h2>{{  aula13 }}</h2>
      <p>Listagem no formato de objeto</p>
      <ul>
        <li v-for="(livro, index) in livros" :key="index">
        {{ livro }}
        </li>
      </ul>
    
    <hr>

    <h2>{{ aula14 }}</h2>
      <p>Listagem no formato de objeto</p>
      <div v-for="(livro, index) in  livros" :key="index">
          <ul>
              <li v-for="valor in livro" :key="valor">
              {{ valor }}
              </li>
          </ul>
      </div> 
    <hr>

    <h2>{{ aula15 }}</h2>
      <div class="quadro" :class="{negrito: importante}">
        <p>Exemplo de quadro</p>

      </div>

     



  </div>
 
</template>

<script>


export default {
  name: 'App',
  components: {},
  data(){
    return{
      titulo: 'Fundamentos Vue.Js',
      aula1: 'Aula 1 - apresentação e exemplo inicial',
      aula2: 'Aula 2 - Interpolação de dados',
      aula3: 'Aula 3 - Renderização Condicional 1 (V-show e V-if)',
      aula4: 'Aula 4 - Renderização Condicional 2 (V-if, V-else-if e V-else)',
      aula5: 'Aula 5 - Métodos',
      aula6: 'Aula 6 - Propriedades Computadas',
      aula7: 'Aula 7 - Manipulação de Eventos 1',
      aula8: 'Aula 8 - Manipulação de Eventos 2',
      aula9: 'Aula 9 - Binding 1',
      aula10: 'Aula 10 - Binding 2 (TWO WAY BINDING)',
      aula11: 'Aula 11 - Renderização de Listas 1',
      aula12: 'Aula 12 - Renderização de Listas 2',
      aula13: 'Aula 13 - Renderização de Listas 3',
      aula14: 'Aula 14 - Renderização de Listas 4',
      aula15: 'Aula 15 - Interligação de classes e estilos 1',
      mensagem: 'Interpolação com Vue.js',
      mensagem2:'',
      mensagem3:'Digite',
      mensagem4:'',
      valor1: 10,
      valor2: 15,
      detalhes: true,
      detalhes1: false,
      url:'https://br.vuejs.org',
      disabled: true,
      disabled2: false,
      frutas:['Laranja, Maçã, Melão'],
      frutas2:[
            {nome:'laranja'},
            {nome:'maçã'},
            {nome: 'melão'}
      ],
      livros:[
        {
          title:'O pequeno Principe',
          autor:'Antonie',
          publicadoEm:'1943',
        },
        {
          title:'Senhor dos Aneis',
          autor:'J.R.R Tolkien',
          publicadoEm:'1954',
        },
      ],
      importante: true,
    }
  },
  methods:{
    boasVindas(){
      return "Seja bem-vindo!"
    },
    verificarParouImpar(valor){
      if(valor % 2 === 0){
        return "PAR"
      } else{
        return "IMPAR"
      }
    },
    inverterMensagem(){
      this.mensagem = this.mensagem.split('').reverse().join('')
    },
    adicionar(){
      this.valor1++
    },
    adicionar2(){
      this.valor2++
    },
    diminuir(){
      this.valor2--
    },
    alterarMensagem(event){
      this.mensagem2 = event.target.value
    },
    alterarMensagem2(event){
      this.mensagem3 = event.target.value
    },
  },
  computed:{
    mensagemInvertida(){
      return this.mensagem.split('').reverse().join('')
    }
  }
}
</script>

<style>
#app {
  font-family: Tahoma, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align:justify;
  color: #2c3e50;
  margin-top: 60px;
}
.negrito{
  font-weight: bold;
}

.quadro{
  width:300px;
  height: 300px;
  border-radius: 20px;
  background-color:aqua;

}
</style>
