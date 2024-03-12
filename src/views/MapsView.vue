<template>
  <div class="maps">
    <div style="display: flex; width: 100%; justify-content: space-between;">
      <div style="width: 48%;">
        <p>MarkerCluster</p>
        <MarkerCluster :apiKey="apiKey" />
      </div>
      <div style="width: 48%;">
        <p>Example</p>
        <Example :apiKey="apiKey" />
      </div>
    </div>
    <div style="display: flex; width: 100%; justify-content: space-between;">
      <div style="width: 48%;">
        <p>Polyline</p>
        <Polyline :apiKey="apiKey" />
      </div>
      <div style="width: 48%;">
        <p>Polylgon</p>
        <Polylgon :apiKey="apiKey" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Maps from "@/components/Maps/Maps.vue";
import Marker from "@/components/Maps/Marker.vue";
import CustomMarker from "@/components/Maps/CustomMarker.vue";
import MarkerCluster from "@/components/Maps/MarkerCluster.vue";
import Polyline from "@/components/Maps/Polyline.vue";
import Polylgon from "@/components/Maps/Polylgon.vue";
import Rectangle from "@/components/Maps/Rectangle.vue";
import Circle from "@/components/Maps/Circle.vue";
import InfoWindow from "@/components/Maps/InfoWindow.vue";
import InfoWindow_2 from "@/components/Maps/InfoWindow_2.vue";
import CustomControl from "@/components/Maps/CustomControl.vue";
import Example from "@/components/Maps/Example.vue";

@Options({
  components: {
    Maps,
    Marker,
    CustomMarker,
    MarkerCluster,
    Polyline,
    Polylgon,
    Rectangle,
    Circle,
    InfoWindow,
    InfoWindow_2,
    CustomControl,
    Example,
  },
})
export default class MapsView extends Vue {
  apiKey: String = "SUA_API_KEY"
 }
</script>
