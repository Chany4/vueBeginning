<template lang="">
  <div>
    {{firstName}} {{lastName}}
    {{object-data}}
  </div>
  <h1>This is the component</h1>
  <slot></slot>
</template>
<script>
export default {
  // props: ['firstName', 'lastName', 'object-data']
}
</script>
<style lang="">

</style>
