<template>
    <v-card outlined class="ma-3" :class="message.name == 'Eu' ? 'purple lighten-2' : 'teal accent-4'">
        <v-card-subtitle class="font-weight-bold"> {{message.name == 'Eu' ? 'Eu' : firstName}} </v-card-subtitle>
        <v-card-text>{{message.text}}</v-card-text>
    </v-card>
</template>