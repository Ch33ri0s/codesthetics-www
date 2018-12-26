<template>
  <div class="footer">
    <span>Created with <icon class="heart" icon="heart"></icon> 2019</span>
  </div>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style lang="scss">

.footer {
  display: flex;
  justify-content: center;
  align-items: center;
  background: #333;
  position: static;
  bottom: 0;
  right: 0;
  left: 0;

  height: 10rem;
  width: 100%;
  span {
    font-size: 1.2rem;
    color: white;
    font-family: 'muliregular', sans-serif;
    font-weight: lighter;
    .heart {
      color: red;
    }
  }
}

</style>
