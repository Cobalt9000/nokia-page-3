<template>
  <div class="taskbar">
    <div class="taskbar-items">
      <div className="bold-text">Digital Twin Site</div>
      </div>
      <div className="taskbar-items center-items"> 
        <div className="taskbar-item">Dashboard</div>
        <div className="taskbar-item">Portfolio</div>
        <div className="taskbar-item">Report</div>
      </div>
      <div className="taskbar-items right-items"> 
        <div className="taskbar-item">
          <FontAwesomeIcon icon={faSearch} className="icon" /> Quick Search
        </div>
        <button
        onclick="window.location.href='https://nokia-page-2.vercel.app/'"
        style="background-color: navy; color: white; padding: 5px 10px; border: none; border-radius: 4px; display: flex; align-items: center; cursor: pointer;"
        >
        <i class="fas fa-map" style="margin-right: 5px;"></i>
        Map Search
        </button>
      </div>
    </div>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { library } from '@fortawesome/fontawesome-svg-core';
import { faSearch, faEllipsisH } from '@fortawesome/free-solid-svg-icons';

library.add(faSearch, faEllipsisH);

export default {
  components: {
    FontAwesomeIcon,
  },
};
</script>