<script>
export default {
  data(){
    return {
      isOpen: false
    }
  },
  methods: {
    onClick() {
      this.isOpen = !this.isOpen
      console.log("click")
    }
  }
}
</script>
<template>
  <button @click="onClick()" type="button" class="p-3 text-white rounded-full bg-primary max-w-36">
    <slot></slot>
  </button>
</template>