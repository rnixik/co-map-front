<script setup lang="ts">
import { GoogleMap, Marker, InfoWindow } from 'vue3-google-map'
import RouteTo from "../components/RouteTo.vue";

const center = { lat: 34.9029804, lng: 32.8673152 }
const caledonia = { lat: 34.9029804, lng: 32.8673152 }
const millomeris = { lat: 34.8836507, lng: 32.8652252 }

const markerOptions = { position: caledonia, label: 'C', title: 'Caledonia Waterfalls' }
const markerOptions2 = { position: millomeris, label: 'M', title: 'Millomeris Waterfalls' }

</script>

<template>
  <GoogleMap
      api-key="AIzaSyBZXbvHZl7EAQbaBnulzV2gne_9H876OpQ"
      style="width: 100%; height: 500px"
      :center="center"
      :zoom="12"
  >
<!--    <Marker :options="markerOptions" />-->
<!--    <InfoWindow :options="{ position: center, content: 'Hello World!' }" />-->
<!--    <InfoWindow :options="{ position: { lat: center.lat, lng: 150.8 } }">-->
<!--      Content passed through slot-->
<!--    </InfoWindow>-->
    <Marker :options="markerOptions">
      <InfoWindow>
        <div id="content">
          <div id="siteNotice"></div>
          <h1 id="firstHeading" class="firstHeading">Caledonia Waterfalls</h1>
          <div id="bodyContent">
            <p>The water of the waterfall falls vertically from a height of 12 meters. According to the season, the surrounding area is covered in lush forest and native wild flowers. Avoiding the nature trail, some choose to walk through a shortcut from Aeodion road through the Psilo Dendro Trout Farm.</p>
            <p>Check the wiki <a href="https://en.wikipedia.org/wiki/Caledonia_Waterfalls">
              page</a>.
            </p>
            <p><RouteTo :lat="caledonia.lat" :lng="caledonia.lng"></RouteTo></p>
          </div>
        </div>
      </InfoWindow>
    </Marker>

    <Marker :options="markerOptions2">
      <InfoWindow>
        <div id="content">
          <div id="siteNotice"></div>
          <h1 id="firstHeading" class="firstHeading">Millomeris Waterfalls</h1>
          <div id="bodyContent">
            <p>The water from the falls cascades from a height of 15 meters, creating a small lake, the level of which rises and sometimes overflows during the winter months, when the volume of water increases significantly.</p>
            <p><RouteTo :lat="millomeris.lat" :lng="millomeris.lng"></RouteTo></p>
          </div>
        </div>
      </InfoWindow>
    </Marker>
  </GoogleMap>
</template>
