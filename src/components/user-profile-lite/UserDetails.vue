<template>
  <d-card class="card-small mb-4 pt-3">

    <!-- Card Header -->
    <d-card-header class="border-bottom text-center">

      <!-- User Avatar -->
      <div class="mb-3 mx-auto">
        <img class="rounded-circle" src="https://cdn1-production-images-kly.akamaized.net/o4NQmi2zrRswzFhtFDVBndz7jd0=/0x0:662x373/673x379/filters:quality(75):strip_icc():format(jpeg)/kly-media-production/medias/1990819/original/038866200_1520932615-Sule__4_.jpg" :alt="user.name" width="200">
      </div>

      <!-- User Name -->
      <h4 class="mb-0">Ken</h4>

      <!-- User Job Title -->
      <span class="text-muted d-block mb-2">pengangguran</span>

    </d-card-header>

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
