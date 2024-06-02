<template>
  <div class="contextbar">
    <div class="context-item">
      <font-awesome-icon :icon="['fas', 'check-circle']" class="icon navy" />
      <span class="text bold">Site Status</span>
    </div>
    <div class="context-item" @click="toggleSurveyDropdown">
      <font-awesome-icon :icon="['fas', 'building']" class="icon navy" />
      <span class="text bold">{{ surveyText }}</span>
      <font-awesome-icon
        :icon="['fas', 'angle-down']"
        :class="{ open: surveyDropdownOpen }"
        class="dropdown-icon"
      />
      <div v-if="surveyDropdownOpen" class="dropdown-content">
        <span @click="handleSurveyItemClick('3D Fly Around View')">3D Fly Around View</span>
        <span @click="handleSurveyItemClick('3D Outdoor Measurement Mode')">3D Outdoor Measurement Mode</span>
        <span @click="handleSurveyItemClick('3D Ground Walk')">3D Ground Walk</span>
        <span @click="handleSurveyItemClick('Detailed Site Images')">Detailed Site Images</span>
      </div>
    </div>
    <div class="context-item" @click="toggleAssetsDropdown">
      <font-awesome-icon :icon="['fas', 'database']" class="icon navy" />
      <span class="text bold">{{ assetsText }}</span>
      <font-awesome-icon
        :icon="['fas', 'angle-down']"
        :class="{ open: assetsDropdownOpen }"
        class="dropdown-icon"
      />
      <div v-if="assetsDropdownOpen" class="dropdown-content">
        <span @click="handleAssetsItemClick('TPA Antenna Positioning Identification')">TPA Antenna Positioning Identification</span>
        <span @click="handleAssetsItemClick('Site Asset Inventory')">Site Asset Inventory</span>
        <span @click="handleAssetsItemClick('Data Download')">Data Download</span>
        <span @click="handleAssetsItemClick('Digital Site Twin')">Digital Site Twin</span>
      </div>
    </div>
    <div class="context-item" @click="toggleAnalyticsDropdown">
      <font-awesome-icon :icon="['fas', 'chart-bar']" class="icon navy" />
      <span class="text bold">{{ analyticsText }}</span>
      <font-awesome-icon
        :icon="['fas', 'angle-down']"
        :class="{ open: analyticsDropdownOpen }"
        class="dropdown-icon"
      />
      <div v-if="analyticsDropdownOpen" class="dropdown-content">
        <span @click="handleAnalyticsItemClick('Antenna Mount Analysis')">Antenna Mount Analysis</span>
        <span @click="handleAnalyticsItemClick('Preliminary Structural Analysis')">Preliminary Structural Analysis</span>
        <span @click="handleAnalyticsItemClick('Tower Space Analysis')">Tower Space Analysis</span>
        <span @click="handleAnalyticsItemClick('RFDS and CD Analysis')">RFDS and CD Analysis</span>
      </div>
    </div>
    <div class="context-item profile-settings">
      <font-awesome-icon :icon="['fas', 'user-cog']" class="icon navy" />
      <span class="text bold">Profile & Settings</span>
    </div>
  </div>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { library } from '@fortawesome/fontawesome-svg-core';
import {
  faCheckCircle,
  faBuilding,
  faDatabase,
  faChartBar,
  faAngleDown,
  faUserCog,
} from '@fortawesome/free-solid-svg-icons';

library.add(
  faCheckCircle,
  faBuilding,
  faDatabase,
  faChartBar,
  faAngleDown,
  faUserCog
);

export default {
  components: {
    FontAwesomeIcon,
  },
  data() {
    return {
      statusDropdownOpen: false,
      surveyDropdownOpen: false,
      assetsDropdownOpen: false,
      analyticsDropdownOpen: false,
      surveyText: 'Digital Survey',
      assetsText: 'Digital Assets',
      analyticsText: 'Digital Analytics',
    };
  },
  methods: {
    toggleSurveyDropdown() {
      this.surveyDropdownOpen = !this.surveyDropdownOpen;
    },
    toggleAssetsDropdown() {
      this.assetsDropdownOpen = !this.assetsDropdownOpen;
    },
    toggleAnalyticsDropdown() {
      this.analyticsDropdownOpen = !this.analyticsDropdownOpen;
    },
    handleSurveyItemClick(item) {
      this.surveyText = item;
      this.$emit('view-selected', item);
      this.surveyDropdownOpen = false;
    },
    handleAssetsItemClick(item) {
      this.assetsText = item;
      this.$emit('view-selected', item);
      this.assetsDropdownOpen = false;
    },
    handleAnalyticsItemClick(item) {
      this.analyticsText = item;
      this.$emit('view-selected', item);
      this.analyticsDropdownOpen = false;
    },
  },
};
</script>