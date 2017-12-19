<template>
  <div class="app" @scroll="updateAppScrollTop({scrollTop: $event.target.scrollTop})">
    <y-header></y-header>
    <!-- <keep-alive> -->
    <router-view></router-view>
    <!-- </keep-alive> -->
  </div>
</template>

<script>
import yHeader from './header/header.vue'
import Vuex from 'vuex'

export default {
  components: {
    yHeader
  },
  mounted() {
    this.untouch()
    setInterval(this.untouch, 15000) // 循环请求未处理订单状态
    this.aUserInfo()
  },
  methods: {
    ...Vuex.mapMutations(['updateAppScrollTop']),
    ...Vuex.mapActions(['untouch', 'aUserInfo']),
  }
}
</script>


<style lang='less'>
* {
  box-sizing: border-box;
}

html {
  background-color: #f2f2f2;
}

html, body, .app {
  height: 100%;
}

body {
  margin: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}

#mum {
  position: absolute;
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  display: none;
  background: rgba(255,255,255,.8) url(https://cdns.007vin.com/img/mum.gif) center no-repeat;
  z-index: 10;
}

.app {
  width: 100%;
  overflow-y: scroll;

  button, input {
    outline: none;
  }

  button {
    cursor: pointer;
  }

  ::-moz-placeholder {
    color: #999;
  }

  .search-icon {
    
  }

  .el-dialog__header {
    text-align: center;
  }

  .el-upload {
    width: 100%;

    .el-upload-dragger {
      width: 100%;
    }
  }
}

</style>
