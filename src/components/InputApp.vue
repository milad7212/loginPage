<template>
    <div>
        <span class="block mb-4 my-2">{{ label }}</span>
          <div class="flex p-2 rounded-lg border border-gray-300">
            <img class="w-6 h-6" :src="`../assets/icons/${icon}`" />
            <input
              class="placeholder:text-xs placeholder:font-bold pr-4 outline-none"
              type="text"
              :placeholder="placeholder"
            />
          </div>
    </div>
</template>

<script>
export default {
  name: 'InputApp',
  props: {
    label: String,
    icon: String,
    placeholder: String
    
  },
  data() {
    return {
      greeting: 'Hello'
    }
  },
  
}
</script>

<style lang="scss" scoped>

</style>