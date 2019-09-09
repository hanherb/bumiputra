<template>
  <d-card class="card-small mb-4 pt-3">

    <!-- Card Header -->
    <d-card-header class="border-bottom text-center">

      <!-- User Avatar -->
      <div class="mb-3 mx-auto">
        <img class="rounded-circle" :src="user.profile_picture" :alt="user.name" width="110">
      </div>

      <!-- User Name -->
      <h4 class="mb-0">{{ user.fullname }}</h4>

      <!-- User Job Title -->
      <span class="text-muted d-block mb-2">{{ user.jobTitle }}</span>

      <!-- User Follow -->
      <d-button pill outline size="sm" class="mb-2"> <i class="material-icons mr-1">person_add</i> Follow</d-button>

    </d-card-header>

    <d-list-group flush>

      <!-- User Performance Report -->
      <d-list-group-item class="px-4">
        <div class="progress-wrapper">
          <strong class="text-muted d-block mb-2">{{ user.performanceReportTitle }}</strong>
          <d-progress class="progress-sm">
            <span class="progress-value">{{ user.performanceReportValue }}%</span>
            <d-progress-bar :max="100" :value="user.performanceReportValue" />
          </d-progress>
        </div>
      </d-list-group-item>

      <!-- User Meta -->
      <d-list-group-item>
        <strong class="text-muted d-block mb-2">{{ user.metaTitle }}</strong>
        <span>{{ user.metaValue }}</span>
      </d-list-group-item>
    </d-list-group>

  </d-card>
</template>

<script>
import address from '@/address';
export default {
  name: 'user-details',
  data(){
    return{
      user: {},
      session: {},
    }
  },

  created: function() 
  {
    this.fetchUser();
  },

  methods: {
    fetchUser() {
      // var id = window.location.href.split("?id=")[1];
      var id = "5c9b31c456ab5400703eaad5";
      this.axios.get(address + ":3000/get-user").then((response) => {
        for (var i = 0; i < response.data.length; i++) {
          if(response.data[i]._id == id) {
            this.user = response.data[i];
            console.log(this.user)
          } 
        }
      });
    },
  }
};
</script>
