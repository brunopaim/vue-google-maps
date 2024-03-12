<template>
  <div ref="mapContainer" style="width: 100%; height: 500px;"></div>
</template>

<script>
import { defineComponent } from "vue";
import { Loader } from "@googlemaps/js-api-loader";

export default defineComponent({
  props: {
    apiKey: String,
  },
  data() {
    return {
      map: null,
      heatmap: null,
    };
  },
  mounted() {
    const loader = new Loader({
      apiKey: apiKey,
      version: "weekly",
    });

    loader.load().then(() => {
      this.initMap();
    });
  },
  methods: {
    initMap() {
      this.map = new google.maps.Map(this.$refs.mapContainer, {
        center: { lat: 37.774546, lng: -122.433523 },
        zoom: 13,
      });

      // Dados do heatmap
      const heatmapData = [
        { location: new google.maps.LatLng(37.782, -122.447), weight: 0.5 },
        new google.maps.LatLng(37.782, -122.445),
        { location: new google.maps.LatLng(37.782, -122.443), weight: 2 },
        { location: new google.maps.LatLng(37.782, -122.441), weight: 3 },
        { location: new google.maps.LatLng(37.782, -122.439), weight: 2 },
        new google.maps.LatLng(37.782, -122.437),
        { location: new google.maps.LatLng(37.782, -122.435), weight: 0.5 },

        { location: new google.maps.LatLng(37.785, -122.447), weight: 3 },
        { location: new google.maps.LatLng(37.785, -122.445), weight: 2 },
        new google.maps.LatLng(37.785, -122.443),
        { location: new google.maps.LatLng(37.785, -122.441), weight: 0.5 },
        new google.maps.LatLng(37.785, -122.439),
        { location: new google.maps.LatLng(37.785, -122.437), weight: 2 },
        { location: new google.maps.LatLng(37.785, -122.435), weight: 3 },
      ];

      // Configuração do heatmap
      this.heatmap = new google.maps.visualization.HeatmapLayer({
        data: heatmapData,
        map: this.map,
      });
    },
  },
});
</script>

<style scoped>
/* Estilos opcionais para o mapa */
#mapContainer {
  height: 100%;
  width: 100%;
}
</style>