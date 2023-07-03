<template>
    <form v-if="selectedItem" @submit.prevent="submitForm" class="form">
      <h2>Выбранный элемент:</h2>
      <div style="margin-bottom: 10px; font-size: 18px">
       <strong>name:</strong>  {{selectedItem.name}}
      </div>
      <div>
        <input class="input" type="text" v-model="tempVal">
      </div>
      <button class="btn">
        добавить изменения
      </button>
    </form>
</template>
<script>
export default {
  name: "ItemForm",
  props:{
    selectedItem: {
      type: Object,
      default: '',
    },
    showDialog: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      tempVal: "",
    };
  },
  methods: {
    submitForm() {
      this.selectedItem.value = this.tempVal;
      this.tempVal = "";
      this.$emit('update:show-dialog', false);
    },
  },
}
</script>

<style scoped>
  .form{
    margin-bottom: 50px;
    width: 100%;

  }
  .input{
    width: 100%;
    height: 40px;
    box-sizing: border-box;
  }
  .btn{
    background: cornflowerblue;
    border: none;
    height: 40px;
    font-size: 18px;
    padding: 5px 15px;
    margin-top: 15px;
    color: white;
    border-radius: 5px;
    cursor: pointer;
  }
</style>