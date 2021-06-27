<template>
  <div class="square" @click="$emit('click', value)">{{ handlePlay }}</div>
</template>

<script>
export default {
  props: {
    value: Number,
    handlePlay: String,
  },
};
</script>

<style scoped>
.square {
  padding: 50px;
  border: 1px solid black;
  max-width: 0px;
  max-height: 0px;
}
</style>
