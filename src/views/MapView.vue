<script setup>
import Header from "../components/Header.vue";
import { latLngBounds, latLng } from "leaflet";
import {
  LMap,
  LControlLayers,
  LTileLayer,
  LMarker,
  LGeoJson,
} from "@vue-leaflet/vue-leaflet";
</script>

<template>
  <Header />
  <div class="fixed">
    <l-map :zoom="zoom" :center="center" style="height: 100vh; width: 100vw">
      <l-control-layers position="topright"></l-control-layers>
      <l-tile-layer
        v-for="tileProvider in tileProviders"
        :key="tileProvider.name"
        :name="tileProvider.name"
        :visible="tileProvider.visible"
        :url="tileProvider.url"
        :attribution="tileProvider.attribution"
        layer-type="base"
      />

      <l-geo-json
        v-for="(geojson, index) in layerData"
        :geojson="geojson"
        :key="index"
        layer-type="overlay"
        :name="`Dusun ${index + 1}`"
      />

      <l-geo-json
        :name="`Landuse`"
        v-if="show"
        :geojson="geojson"
        :options="options"
        layer-type="overlay"
        :options-style="styleFunction"
      />
      <l-marker :lat-lng="marker" />
    </l-map>
  </div>
</template>

<script>
const tileProviders = [
  {
    name: "Esri Imageri",
    visible: true,
    url: "https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}",
    attribution:
      "Tiles &copy; Esri &mdash; Source: Esri, i-cubed, USDA, USGS, AEX, GeoEye, Getmapping, Aerogrid, IGN, IGP, UPR-EGP, and the GIS User Community",
  },
  {
    name: "OpenStreetMap",
    visible: false,
    attribution:
      '&copy; <a target="_blank" href="http://osm.org/copyright">OpenStreetMap</a> contributors',
    url: "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
  },
];

export default {
  name: "Leaflet",
  components: {
    LMap,
    LControlLayers,
    LTileLayer,
    LGeoJson,
    LMarker,
  },
  data() {
    return {
      loading: false,
      show: true,
      enableTooltip: true,
      zoom: 15,
      center: [-3.28561, 120.97431],
      layerData: [],
      geojson: null,
      fillColor: "#0CF9E0",
      tileProviders: tileProviders,
      marker: latLng(-3.28561, 120.97431),
      timeout: undefined,
    };
  },
  mounted() {
    this.timeout = setTimeout(this.loadSomeGeoJson, 1000);
  },
  beforeDestroy() {
    if (this.timeout) {
      clearTimeout(this.timeout);
    }
  },

  methods: {
    async loadSomeGeoJson() {
      const nextIndex = this.layerData.length;

      const response = await fetch("/ds_nyule.geojson");
      const data = await response.json();

      console.log(data);

      if (nextIndex >= data.features.length) {
        return;
      }

      this.layerData.push(data.features[nextIndex]);

      this.timeout = setTimeout(this.loadSomeGeoJson, 5000);
    },
  },

  computed: {
    options() {
      return {
        onEachFeature: this.onEachFeatureFunction,
      };
    },
    styleFunction() {
      const fillColor = this.fillColor; // important! need touch fillColor in computed for re-calculate when change fillColor
      return () => {
        return {
          weight: 2,
          color: "#000000",
          opacity: 1,
          fillColor: fillColor,
          fillOpacity: 0.5,
        };
      };
    },
    onEachFeatureFunction() {
      if (!this.enableTooltip) {
        return () => {};
      }
      return (feature, layer) => {
        layer.bindTooltip(
          "<div>Nama:" +
            feature.properties.nama +
            "</div><div>Luas: " +
            feature.properties.luas +
            " Ha</div>",
          { permanent: false, sticky: true }
        );
      };
    },
  },
  async created() {
    this.loading = true;
    const response = await fetch("/lu_ds_nyule.geojson");
    const data = await response.json();
    this.geojson = data;
    this.loading = false;
  },
};
</script>
