<template>
  <v-layout row wrap>
    <v-flex xs4>
      <v-card>
      <v-card-title primary title>
        <div>
          <div class="headline">Produto A</div>
          <span class="grey--text">Data</span>
        </div>
      </v-card-title>
      <v-card-text>Descrição do produto</v-card-text>
      <v-card-actions>
        <v-btn flat color="red">Ver informações</v-btn>
        <v-spacer></v-spacer>
      </v-card-actions>
      </v-card>
    </v-flex>

    <v-flex xs4>
      <v-card>
        <v-card-title primary title>
          <div>
            <div class="headline">Produto B</div>
            <span class="grey--text">Data</span>
          </div>
        </v-card-title>
        <v-card-text>Descrição do produto</v-card-text>
        <v-card-actions>
          <v-btn flat color="purple">Ver informações</v-btn>
          <v-spacer></v-spacer>
        </v-card-actions>
      </v-card>
    </v-flex>

    <v-flex xs4>
      <v-card>
      <v-card-title primary title>
        <div>
          <div class="headline">Produto C</div>
          <span class="grey--text">Data</span>
        </div>
      </v-card-title>
      <v-card-text>Descrição do produto</v-card-text>
      <v-card-actions>
        <v-btn flat color="red">Ver informações</v-btn>
        <v-spacer></v-spacer>
      </v-card-actions>
      </v-card>
    </v-flex>

    <v-flex xs4>
      <v-card>
        <v-card-title primary title>
          <div>
            <div class="headline">Produto D</div>
            <span class="grey--text">Data</span>
          </div>
        </v-card-title>
        <v-card-text>Descrição do produto</v-card-text>
        <v-card-actions>
          <v-btn flat color="purple">Ver informações</v-btn>
          <v-spacer></v-spacer>
        </v-card-actions>
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
      produtos: []
    }
  },
  mounted () {
    this.fetchProdutos()
  },
  methods: {
    async fetchProdutos () {
      return axios({
        method: 'get',
        url: 'http://localhost:8080/produtos'
      })
        .then((response) => {
          this.produtos = response.data
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
