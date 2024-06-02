<template>
  <div class="app">
    <TaskbarComponent />
    <MenuBarComponent />
    <div class="content">
      <div class="left-pane">
        <ContextbarComponent @view-selected="handleViewSelected" />
      </div>
      <div
        class="middle-pane"
        :class="{ 'full-screen': isMiddlePaneFullScreen }"
        @click="toggleMiddlePaneFullScreen"
      >
        <component :is="activeComponent" />
      </div>
      <div class="right-pane">
        <!-- Right pane content -->
      </div>
    </div>
  </div>
</template>

<script>
import TaskbarComponent from './components/TaskbarComponent.vue';
import MenuBarComponent from './components/MenuBarComponent.vue';
import ContextbarComponent from './components/ContextbarComponent.vue';
import DigitalTwinSite from './components/DigitalSiteTwin.vue';

export default {
  components: {
    TaskbarComponent,
    MenuBarComponent,
    ContextbarComponent,
    DigitalTwinSite,
  },
  data() {
    return {
      isMiddlePaneFullScreen: false,
      activeComponent: null,
    };
  },
  methods: {
    handleViewSelected(view) {
      switch (view) {
        case 'Digital Site Twin':
          this.activeComponent = DigitalTwinSite;
          break;
        // Add cases for other views as needed
        default:
          this.activeComponent = null;
          break;
      }
    },
    toggleMiddlePaneFullScreen() {
      this.isMiddlePaneFullScreen = !this.isMiddlePaneFullScreen;
    },
  },
};
</script>