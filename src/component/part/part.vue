<template>
  <div class="part-container">
    <p-search />
    <div class="part-result">
      <router-view />
    </div>
  </div>
</template>


<script>
import pSearch from './search.vue'
import pSelector from './selector.vue'
import pDetail from './detail/detail.vue'

export default {
  components: {
    pSearch,
    pSelector,
    pDetail
  },
  computed: {

  },
  methods: {
    
  }
};
</script>

<style lang="less" scoped>
.part-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;

  @d8line: 1px solid #d8d8d8;

  .part-result {
    width: 1024px;
    min-height: 368px;
    background: url(/static/img/p_yhc.png) center ~"/" 200px auto no-repeat;

    div {
      font-size: 14px;
      color: #333;
    }
  }
}
</style>
