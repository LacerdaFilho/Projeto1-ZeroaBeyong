<template>
  <v-app>
    <v-main>
      <v-app-bar color="green">{{nome}}</v-app-bar>
        <div v-for="(message, index) in messages" :key="index" class="message-container">
          <v-card outlined class="ma-3" :class="message.name == 'Eu' ? 'purple lighten-2' : 'teal accent-4'">
            <v-card-subtitle class="font-weight-bold"> {{message.name}} </v-card-subtitle>
            <v-card-text>{{message.text}}</v-card-text>
          </v-card>
          <v-card v-else outlined class="ma-3 purple accent-4">
            <v-card-subtitle class="font-weight-bold"> {{message.name}} </v-card-subtitle>
            <v-card-text>{{message.text}}</v-card-text>
          </v-card>
        </div>
      <v-app-bar color="#424242" bottom fixed>
        <v-text-field @keyup.enter="sendMessage" v-model="campo_text" solo hide-details label="Enviar mensagem ..."></v-text-field>
        <v-btn @click="sendMessage" x-large icon color="blue"></v-btn>
        <v-icon>mdi-send</v-icon>
      </v-app-bar>
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        nome: "Roberto",
        messages: [
          {
            name: "Roberto Silva",
            text: "Olá"
          },
          {
            name: "Roberto Silva",
            text: "Tudo bem ?"
          },
          {
            name: "Eu",
            text: "Tudo bem !"
          },
        ],
        campo_text: ""
      }
    },
    methods: {
      sendMessage() {
        let message = {
          name: "Eu",
          text: this.campo_text
        }
        this.messages.push(message)
        this.campo_text = ""
      }
    }
  }
</script>
