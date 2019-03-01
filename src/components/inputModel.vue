<template>
  <div>
    <input type="text" v-model="val2" v-on="$listeners"   />
  </div>
</template>

<script>
export default {
  name: 'inputModel',
  model: {
    prop: 'val',
    event: 'lalala'
  },
  props: ['val'],
  created() {
    // $listeners是一个对象，里面包含了作用在这个组件上的所有监听器
    // console.log('v-model', this.$listeners)
  },
  data() {
    return {
    }
  },
  computed: {
    val2: {
      get: function () {
        return this.val
      },
      set: function (newVal) {
        this.$emit('lalala', newVal)
      }
    }
  }
}
</script>