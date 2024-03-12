<template>
  <div class="maps">
    <Marker :apiKey="apiKey" />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Marker from "@/components/Maps/Marker.vue";

@Options({
  components: {
    Marker,
  },
})
export default class MapsView extends Vue { 
  apiKey: String = "SUA_API_KEY"
}
</script>
