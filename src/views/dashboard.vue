<template>
  <section class="page-layout">
      <sidebar @toggle-sidebar="toggleSidebar" :visible="showSidebar" />
      <div class="main-content">
        <navbar></navbar>
        <div style="margin:0px 0px 10px 40px">
         <button class="button nav-opener" @click="toggleSidebar">O</button>
        </div>
         
      </div>
  </section>
</template>

<script>
import navbar from '../components/navbar.vue'
import Sidebar from '../components/sidebar.vue'
export default {
  components: { 
    Sidebar,
    navbar,
  },
  data:() => ({
    showSidebar: false,
  }),
  methods: {
    toggleSidebar() {
        this.showSidebar = !this.showSidebar
    },
  }
}
</script>
<style scoped>
.page-layout {
    display: flex;
    align-items: flex-start;
    background: #f5f8fa;
    min-height: 100vh;
}
.page-layout .main-content {
    margin-left: 247px;
    flex: 1;
}
@media screen and (max-width: 1200px) {
    .page-layout .main-content {
        margin-left: 0;
}
}
.content-wrapper {
    padding: 0 40px;
    display: flex;
    gap: 20px;
    flex: 1;
}

@media screen and (max-width: 576px) {
    .header {
    align-items: flex-start;
    flex-direction: column;
}
    .header .actions {
    margin-left: auto;
    margin-top: 8px;
}
}

@media screen and (max-width: 1200px) {
    .page-layout .right-checkbox {
        display: none;
    }
    }
    .nav-opener {
        display: none;
        font-size: 24px;
    }
    @media screen and (max-width: 1200px) {
        .nav-opener {
            display: inline-block;
    }
}
 
</style>