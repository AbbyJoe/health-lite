<template>
  <div class="sidebar" :class="{ visible: visible }">
    <div class="side-header">
      <div class="logo">
        <logo></logo>
      </div>
      <div class="name">
        <router-link to="/">
          <p>Health Lite</p>
        </router-link>
      </div>
    </div>
    <ul class="sidebar__content">
      <li>
        <router-link :to="{ name: 'dashboard' }">
          <dashlogo/>
          Dashboard
        </router-link>
      </li>
      <li>
        <router-link :to="{ name: 'dashboard' }">
          <waitingIcon/>
          Waiting Room
        </router-link>
      </li>
      <li>
        <router-link :to="{ name: 'dashboard' }">
        <scheduleIcon/>
        Schedule
        </router-link>
      </li>
      <li>
        <router-link :to="{ name: 'dashboard'}">
          <patientIcon/>
          My Patients
        </router-link>
      </li>
      <li>
        <router-link :to="{ name: 'dashboard' }">
          <notesIcon/>
          Notes
        </router-link>
      </li>
      <li>
        <router-link :to="{ name: 'dashboard' }">
        <chatIcon/>
          Chats
        </router-link>
      </li>
    </ul>
    <ul>
        <li>
            <router-link :to="{ name: 'profile' }">
            <sideAvatar/>
            My Profile
            </router-link>
        </li>
        <li>
            <router-link :to="{ name: 'profile' }">
            <settingsIcon/>
            settings
            </router-link>
        </li>
    </ul>
    <span style="font-size:30px; color: #fff" @click="$emit('toggle-sidebar')" class="close button">&times;</span>
  </div>
</template>

<script>
import logo from '@/components/icons/logo.vue'
import dashlogo from '@/components/icons/dashlogo.vue'
import waitingIcon from '@/components/icons/waitingIcon.vue'
import scheduleIcon from '@/components/icons/scheduleIcon.vue'
import patientIcon from '@/components/icons/patientIcon.vue'
import notesIcon from '@/components/icons/notesIcon.vue'
import chatIcon from '@/components/icons/chatIcon.vue'
import sideAvatar from '@/components/icons/sideAvatar.vue'
import settingsIcon from '@/components/icons/settingsIcon.vue'

export default {
  components: { 
    logo,
    dashlogo,
    waitingIcon,
    scheduleIcon,
    patientIcon,
    notesIcon,
    chatIcon,
    sideAvatar,
    settingsIcon
  },
  name: "sidebar",
  props: {
    visible: {
      type: Boolean,
      required: true,
      default: false,
    },
  },
  methods: {
  },
  emits: ["toggle-sidebar"],
}
</script>

<style scoped>
.sidebar {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	max-width: 247px;
	min-height: 100vh;
	height: 100%;
	background: #1565D8;
    color: #fff;
    box-shadow: inset -1px 0px 0px #a6adb4;
	padding: 25px 25px 0px 27px;
	flex-shrink: 0;
}
 .sidebar .side-header {
	display: inline-flex;
	align-items: center;
	gap: 8px;
	cursor: pointer;
	margin-bottom: 40px;
}
 .sidebar .side-header .logo {
	width: 36px;
	height: 36px;
	border-radius: 50%;
    margin-left: 15px;
}
.sidebar .side-header .name a { 
    text-decoration: none;
}
 .sidebar .side-header .name p {
	font-weight: 900;
    font-size: 18px;
    line-height: 21px;
	color: #fff;
}
 .sidebar .side-header .name p i {
	margin-left: 5px;
	color: #4f566b;
	font-size: 14px;
}
 .sidebar ul {
	list-style: none;
}
 .sidebar ul li {
	margin-bottom: 12px;
    padding: 0px 0px 25px 20px;
}
 .sidebar ul li a {
	display: flex;
	align-items: center;
	gap: 18px;
	outline: none;
	text-decoration: none;
	font-weight: 500;
    font-size: 16px;
    line-height: 19px;
	color: #fff;
}
 .sidebar ul li a.router-link-active {
	font-weight: 400;
	color: #fff;
}
 .sidebar ul.sidebar__content {
	margin-bottom: 80px;
    margin-top: 20px;
}
 @media screen and (max-width: 1200px) {
	.sidebar {
	transform: translateX(-320px);
	transition: all 0.3s linear;
	}
	.sidebar.visible {
	transform: translateX(0);
	}
}
 .sidebar .close {
	position: absolute;
	right: 15px;
	top: 25px;
	font-size: 20px;
	color: #4f566b;
	display: none;
}
 @media screen and (max-width: 1200px) {
	.sidebar .close {
	display: block;
	}
}
 
</style>