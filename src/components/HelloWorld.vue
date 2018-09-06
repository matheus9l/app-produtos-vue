<template>
  <v-layout row wrap>

  <v-flex xs4 v-for="p in cep" :key="p.id">
      <v-card>
        <v-card-title primary-title>
          <div>
            <div class="headline">
              <v-btn flat v-bind:to="`/produtos/${p.id}`">
                {{ p.nome }}
              </v-btn>
            </div>
            <span class="grey--text">{{ p.sigla }}</span>
          </div>
        </v-card-title>
        <!-- <v-card-text>
          <v-btn outline color="indigo" v-bind:to="`/produtos/${p.id}`">{{ p.urlImagem }}</v-btn>
        </v-card-text> -->
      </v-card>
    </v-flex>

  </v-layout>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HelloWorld',
  data () {
    return {
      cep: []
    }
  },
  mounted () {
    this.fetchProdutos()
  },
  methods: {
    async fetchProdutos () {
      return axios({
        method: 'get',
        url: 'https://servicodados.ibge.gov.br/api/v1/localidades/estados'
      })
        .then((response) => {
          this.cep = response.data
          console.log(this.cep)
        })
        .catch(() => {
        })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
