<template>
  <div class="base-layout">
 
    <slot name="header"></slot>

    <slot name="main"></slot>


    <slot name="footer"></slot>
  </div>
</template>

<style scoped>
.base-layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

</style>