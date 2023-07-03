<template>
  <div @click="selectItem(item)" class="item" v-for="item in info" :key="item.id">
      <div>
        <strong>name:</strong> {{item.name}}
      </div>
      <div>
        <strong>value:</strong> {{item.value}}
      </div>
  </div>
</template>

<script>
export default {
  name: "ItemsList",
  props:{
    info:{
      type: Array,
      required: true
    }
  },
  methods:{
    selectItem(item){
      this.$emit('item-selected', item);
    }
  }
}
</script>

<style scoped>
.item{
  width: 100%;
  border: 1px solid green;
  margin-top: 15px;
  padding: 5px 10px;
  border-radius: 5px;
  cursor: pointer;
  box-sizing: border-box;
}
.item div{
  font-size: 18px;
}
.item div:nth-child(1){
  margin-bottom: 5px;
}
</style>