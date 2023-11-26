<template>
  <div class="price_content-progress-wrapper">
    <p class="progress_header">Your data is not fully being reported</p>
    <div class="progress">
      <div class="progress_group">
        <div class="progress_background red">
          <div class="progress_indicator"></div>
        </div>
      </div>
    </div>
    <div class="progress_bottom">
      <div class="critical_info">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="15"
          viewBox="0 0 16 15"
          fill="none"
        >
          <ellipse cx="8" cy="7.5" rx="6.25" ry="6.25" fill="#FF4A3D" />
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M8 4.375C8.34518 4.375 8.625 4.65482 8.625 5L8.625 7.8125C8.625 8.15768 8.34518 8.4375 8 8.4375C7.65482 8.4375 7.375 8.15768 7.375 7.8125L7.375 5C7.375 4.65482 7.65482 4.375 8 4.375Z"
            fill="white"
          />
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M8 9.0625C8.34518 9.0625 8.625 9.34232 8.625 9.6875L8.625 10C8.625 10.3452 8.34518 10.625 8 10.625C7.65482 10.625 7.375 10.3452 7.375 10L7.375 9.6875C7.375 9.34232 7.65482 9.0625 8 9.0625Z"
            fill="white"
          />
        </svg>
        <p class="progress_left_text red">You’re missing 20% of your data</p>
      </div>
      <p class="progress_right_text">
        Your Revenue: <span class="progress_right_text_bold">48k</span>
      </p>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({})
</script>

<style scoped>
.price_content-progress-wrapper {
  display: flex;
  width: 427px;
  padding: 20px 16px;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  gap: 16px;
  border-radius: 8px;
  border: 1px solid #e6e7e8;
  background: #fff;
  box-shadow: 0px 6px 12px 0px rgba(26, 40, 53, 0.05);
}

.progress_header {
  color: #5a5c60;
  font-family: Montserrat;
  font-size: 20px;
  font-style: normal;
  font-weight: 700;
  line-height: 18px; /* 128.571% */
  padding: 0;
  margin: 0;
}

.progress {
  display: flex;
  height: 8px;
  align-items: center;
  gap: 10px;
  align-self: stretch;
  border-radius: 360px;
  border: 0.5px solid #677078;
}

.progress_group {
  height: 8px;
  flex: 1 0 0;
}

.progress_background {
  width: 100%;
  height: 8px;
  flex-shrink: 0;
  border-radius: 360px;
  background: #e6e7e8;
}

.progress_background.red {
  background: #d05047;
}

.progress_indicator {
  width: 376.812px;
  height: 8px;
  flex-shrink: 0;
  border-radius: 360px;
  background: #0b7448;
}

.progress_bottom {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 4px;
  align-self: stretch;
}

.progress_left_text {
  padding: 0;
  margin: 0;
  color: #1a2835;
  font-family: Montserrat;
  font-size: 12px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  flex: 1 0 0;
}

.progress_left_text.red {
  color: #ff4a3d;
}

.critical_info {
  display: flex;
  align-items: center;
  gap: 4px;
}

.progress_right_text {
  padding: 0;
  margin: 0;
  color: #1a2835;
  text-align: right;
  font-family: Montserrat;
  font-size: 12px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
}

.progress_right_text_bold {
  font-weight: 700;
}
</style>
