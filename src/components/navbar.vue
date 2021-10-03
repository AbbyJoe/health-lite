<template>
  <div class="navbar">
    <ul class="icons">
      <li>
        <router-link to="/">
        <notification/>
        </router-link>
      </li>
      <li>
        <router-link to="/">
        <profile/>
        </router-link>
      </li>
    </ul>
  </div>
</template>

<script>
import notification from '@/components/icons/notifications.vue'
import profile from '@/components/icons/profile.vue'

export default {
  name: "TheNavbar",
  components: {
    notification,
    profile
  }
}
</script>
<style scoped>
.navbar {
	padding: 20px 40px 20px 20px;
	display: flex;
	justify-content: flex-end;
	align-items: center;
	margin-bottom: 15px;
    background-color: #fff;
}
 .navbar .icons {
	list-style: none;
	display: flex;
	align-items: center;
	gap: 16px;
}
 
</style>