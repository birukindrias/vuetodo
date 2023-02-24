<script >
export default {
  data() {
    return {
      msg: 'mainhome',
      val: 2,
      array: ['name'],
      txt: 'main',
      indexofval: 0
    }
  },
  methods: {
    valadd() {
      return this.val++;
    },
    add() {
      return this.array.unshift(this.txt)
    }, selected(el) {
      console.log(this.array[el]);
      this.indexofval = this.array[el]
      // console.log(this.indexofval);
    }
    ,
    update() {
      this.array[this.indexofval] = this.txt

      console.log(this.array[this.indexofval]);

    }

    ,
    dele() {
      this.array.pop([this.indexofval])

    }
  },
}
</script>

<template>
  <main>
    {{ val }}
    <div v-for="(ar, index) in array" :key="index">
      <div @click="selected(index)">
        {{ ar }}

      </div>
    </div>
    <input v-model="txt">

    <button @click="add">ad</button>
    <button @click="update">update</button>
    <button @click="dele">dele</button>
  </main>
</template>
