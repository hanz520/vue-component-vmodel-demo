<template>
  <div>
    <input-sync :val.sync="val" @focus="inputFn"></input-sync>

    <input-model v-model="val" @focus.native="inputFn2"></input-model>
    
    <button @click="viewFn">查看</button>
    <button @click="changeFn">修改</button>
  </div>
</template>

<script>
import inputSync from '@/components/inputSync.vue'
import inputModel from '@/components/inputModel.vue'
export default {
  components: {
    inputSync,
    inputModel
  },
  data() {
    return {
      val: 'hanz'
    }
  },
  methods: {
    viewFn() {
      console.log(this.val)
    },
    changeFn() {
      this.val = 'lee'
      console.log(this.val)
    },    
    inputFn() {
      console.log('sync', this.val)
    },
    inputFn2() {
      console.log('model', this.val)
    }
  }
  // watch: {
  //   val() {
  //     console.log(this.val)
  //   }
  // }
}
</script>
