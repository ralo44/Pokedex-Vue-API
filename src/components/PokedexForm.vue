<template>
    <form class="pokemon-form" v-on:submit="handleSubmit">
        <input
            class="pokemon-input"
            type="text"
            name="pokemon"
            v-model="pokemonName"
            placeholder="Ingresa el pokemon"
            autocomplete="off"
        />
        <input type="submit"
            class="pokemon-btn"
            value="Go"
        />
    </form>
</template>

<script>
export default {
  name: 'PokedexForm',
  data () {
    return {
      pokemonName: ''
    }
  },
  methods: {
    handleSubmit (e) {
      e.preventDefault()
      const pokemonName = this.pokemonName
      const newPokemonId = window.isNaN(parseInt(pokemonName)) ? pokemonName.toLowerCase() : pokemonName
      this.$emit('submit', newPokemonId)
      console.log(this.newPokemonId)
    }
  }
}
</script>
