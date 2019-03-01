<template>
  <div class="input">
    <input type="text" v-model="val1" v-on="$listeners"  />
  </div>
</template>

<script>
export default {
  name: 'inputSync',
  created() {
    console.log(this.$listeners.focus)
  },
  props: ['val'],
  data() {
    return {
    }
  },
  computed: {
    val1: {
      get: function() {
        return this.val
      },
      set: function(newVal) {
        this.$emit('update:val', newVal)
      }
    }
  }
}
</script>

<style>
.input{
background: rgb(211, 211, 205);
padding: 20px;
}
</style>
