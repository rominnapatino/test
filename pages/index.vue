<template>
  <v-data-table
    :headers="headers"
    :items="monedas"
    :items-per-page="10"
    class="elevation-1"
  :footer-props="{itemsPerPageText: 'Monedas por página'}"
  >
    <template v-slot:[`item.image`]="{ item }">
      <div class="p-2">
        <v-img :src="item.image" :alt="item.name" width="50"></v-img>
      </div>
    </template>
  </v-data-table>
</template>

<script>
import axios from 'axios'
var url = 'https://api.coingecko.com/api/v3/exchanges';
export default {
  data(){
    return{ headers: [
          { text: 'Logo', value: 'image', sortable: false, width: 50},
          { text: 'Nombre', value: 'name', width: 150},
          { text: 'País', value: 'country', width: 150 },
          { text: 'Descripción', value: 'description', width: 250  },
          { text: 'Sitio web', value: 'url', width: 250 },
        ],
        monedas:[]
  }},

  created(){
    axios.get(url)
    .then(response =>{
      this.monedas = response.data
    }).catch(error => {
    console.log(error)
    });
  },
}
</script>
