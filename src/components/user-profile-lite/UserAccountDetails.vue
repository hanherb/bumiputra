<template>
  <d-card class="card-small mb-4">

    <!-- Card Header -->
    <d-card-header class="border-bottom">
      <h6 class="offset-lg-4">Marketing Tools</h6>
    </d-card-header>

    <d-list-group flush>
      <d-list-group-item class="p-3">
        <d-row>
          <d-col class="offset-lg-0">
            <d-button-group vertical class="col-lg-12">
                <d-button>Button 1</d-button>
                <d-button>Button 2</d-button>
                <d-button>Button 2</d-button>
                <d-button>Button 2</d-button>
                <d-button>Button 2</d-button>
            </d-button-group>
          </d-col>
        </d-row>
      </d-list-group-item>
    </d-list-group>
  </d-card>
</template>

<script>
export default {
  name: 'user-account-details',
  props: {
    /**
     * The component title.
     */
    title: {
      type: String,
      default: 'Account Details',
    },
  },
};
</script>
