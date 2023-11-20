<template>
  <div class="join">
  <button class="join-item btn btn-sm">1</button>
  <button class="join-item btn btn-sm btn-active">2</button>
  <button class="join-item btn btn-sm">3</button>
  <button class="join-item btn btn-sm">4</button>
  <pre>{{ jsonData  }}</pre>
</div>
</template>

<script>

const pagination = {
  myJsonData: {
    type: Object,
    required: true
  }
}

export default {
  
  mounted() {
    // mounted 時，先取得一次資料
    console.log('pagination:',myJsonData)
   
  },
}
</script>

<style>

</style>