<template>
  <GoogleMap :api-key="apiKey" style="width: 100%; height: 500px" :center="center" :zoom="4">
    <Marker :options="{ position: center }">
      <InfoWindow v-model="infowindow">
        <div id="content">
          This is the infowindow content
        </div>
      </InfoWindow>
    </Marker>
  </GoogleMap>
</template>

<script>
import { defineComponent, ref } from "vue";
import { GoogleMap, Marker, InfoWindow } from "vue3-google-map";

export default defineComponent({
  props: {
    apiKey: String,
  },
  components: { GoogleMap, Marker, InfoWindow },
  setup() {
    const center = { lat: -25.363, lng: 131.044 };
    const infowindow = ref(true); // Will be opened when mounted

    return { center, infowindow };
  },
  watch: {
    infowindow(v) {
      alert('infowindow has been ' + (v ? 'opened' : 'closed'))
    }
  }
});
</script>