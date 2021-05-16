<template>
  <div>
    <div class="header">
      <div class="header_left">
        <p>{{ heading }}</p>
        <font-awesome-icon class="header-icon" :icon="['fa', 'folder']" />
        <font-awesome-icon class="header-icon"  :icon="['fa', 'star']" />
        <!-- <i class="fa fa-folder-o" aria-hidden="true"></i> -->
      </div>
      <div class="header_right">
        <font-awesome-icon class="header-icon"  :icon="['fa', 'stop-circle']" />
        <font-awesome-icon class="header-icon"  :icon="['fa', 'eye']" />
        <font-awesome-icon  class="header-icon" :icon="['fa', 'cog']" />
        <button>Send</button>
        <font-awesome-icon class="header-icon"  :icon="['fa', 'ellipsis-v']" />
      </div>
    </div>
    <div>
      
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    heading: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header {
  background: #fff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 40px;
  .header_left{
    display: flex;
    justify-content: space-between;
    align-items: center;
    p {
      font-size: 24px;
    }
  }
  .header_right {
    display: flex;
    justify-content: space-between;
    align-items: center;
    button {
      background: #673ab6;
      padding: 5px 15px;
      color: #fff;
      border-radius: 5px;
    }
  }
  .header-icon {
    margin: 10px 12px;
  }
}
</style>
