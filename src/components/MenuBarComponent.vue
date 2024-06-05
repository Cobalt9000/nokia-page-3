<template>
  <div class="menu-bar">
    <div class="menu-left">
      <span class="date">{{ today }}</span>
      <span class="site-info">
        <font-awesome-icon :icon="['fas', 'building']" class="icon" /> Site Name
      </span>
    </div>
    <div class="menu-right">
      <span class="tower-height">
        <font-awesome-icon :icon="['fas', 'broadcast-tower']" class="icon" /> Tower Height
      </span>
      <span class="location">
        <font-awesome-icon :icon="['fas', 'map-marker-alt']" class="icon" /> Location
      </span>
      <span class="site-type">
        <font-awesome-icon :icon="['fas', 'broadcast-tower']" class="icon" /> Site Type
      </span>
    </div>
  </div>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { library } from '@fortawesome/fontawesome-svg-core';
import { faBuilding, faMapMarkerAlt, faBroadcastTower } from '@fortawesome/free-solid-svg-icons';

library.add(faBuilding, faMapMarkerAlt, faBroadcastTower);

export default {
  components: {
    FontAwesomeIcon,
  },
  data() {
    return {
      today: new Date().toLocaleDateString(),
    };
  },
};
</script>