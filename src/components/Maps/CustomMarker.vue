<template>
  <GoogleMap :api-key="apiKey" style="width: 100%; height: 500px" :center="center" :zoom="15">
    <CustomMarker :options="{ position: center, anchorPoint: 'BOTTOM_CENTER' }">
      <div style="text-align: center">
        <div style="font-size: 1.125rem">Vuejs Amsterdam</div>
        <img src="https://vuejs.org/images/logo.png" width="50" height="50" style="margin-top: 8px" />
      </div>
    </CustomMarker>
  </GoogleMap>
</template>

<script>
import { defineComponent } from 'vue'
import { GoogleMap, CustomMarker } from 'vue3-google-map'

export default defineComponent({
  props: {
    apiKey: String,
  },
  components: { GoogleMap, CustomMarker },
  setup() {
    const center = { lat: 52.36834, lng: 4.88635 }

    return { center }
  },
})
</script>