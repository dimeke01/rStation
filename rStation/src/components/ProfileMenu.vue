<template>
  <div class="col-sm-3">
    <ul class="menu-list">
      <li class="menu-list-item" @click="$router.push('/profile')">
        <i class="fas fa-user-circle"></i>
        <span>Profile</span>
      </li>
       <li class="menu-list-item" @click="$router.push('/stations')" v-if="isManager">
        <i class="fas fa-place-of-worship"></i>
        <span>Stations</span>
      </li>
      <li class="menu-list-item" @click="$router.push('/pick-routes')" v-if="isManager">
        <i class="fas fa-map-marked-alt"></i>
        <span>Routes</span>
      </li>
      <li class="menu-list-item" @click="$router.push('/employer')" v-if="isManager">
        <i class="fas fa-user"></i>
        <span>Employees</span>
      </li>

      <li class="menu-list-item" @click="$router.push('/bookings')">
        <i class="fas fa-history"></i>
        <span>Bookings</span>
      </li>
      <!-- <li class="menu-list-item" @click="$router.push('/settings')">
        <i class="fas fa-user-cog"></i>
        <span>Settings</span>
      </li> -->

      <li class="menu-list-item" @click="$router.push('/login')">
        <i class="fas fa-power-off"></i>
        <span>Sign out</span>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data(){
    return{
      isManager: false
    }
  },
  mounted: function(){
    if(localStorage.manager === 'true'){
      this.isManager = localStorage.manager
    }
  }
};
</script>
<style lang="scss" scoped>
.menu-list {
  margin: auto 12px auto 0;
  padding: 0;
  .menu-list-item {
    list-style: none;
    border-top: 1px solid rgba(0, 0, 0, 0.1);
    background: linear-gradient(to left, #00ff99 0%, #33ccff 100%);
    padding: 8px;
    font-size: 16px;
    span {
      font-weight: 350;
    }
    i {
      width: 24px;
      margin: auto 4px auto 4px;
    }
  }
  .menu-list-item:hover {
    background: #33ccff;
    cursor: pointer;
  }
  .menu-list-item:first-of-type {
    border: none;
    border-top-left-radius: 5px;
    border-top-right-radius: 6px;
  }
  .menu-list-item:last-of-type {
    border-top: 1px solid rgba(0, 0, 0, 1);
    border-bottom-left-radius: 6px;
    border-bottom-right-radius: 6px;
  }
}
</style>
