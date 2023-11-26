<template>
  <div class="price__banner-wrapper" :class="{ red: type === 'critical' }">
    <div class="price__banner-left">
      <svg
        v-if="type === 'warning'"
        xmlns="http://www.w3.org/2000/svg"
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
      >
        <ellipse cx="12" cy="12" rx="10" ry="10" fill="#B7A222" />
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M12 7C12.5523 7 13 7.44772 13 8L13 12.5C13 13.0523 12.5523 13.5 12 13.5C11.4477 13.5 11 13.0523 11 12.5L11 8C11 7.44772 11.4477 7 12 7Z"
          fill="white"
        />
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M12 14.5C12.5523 14.5 13 14.9477 13 15.5L13 16C13 16.5523 12.5523 17 12 17C11.4477 17 11 16.5523 11 16L11 15.5C11 14.9477 11.4477 14.5 12 14.5Z"
          fill="white"
        />
      </svg>
      <svg
        v-if="type === 'critical'"
        xmlns="http://www.w3.org/2000/svg"
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
      >
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M3.95434 17C3.21148 17 2.57964 16.5813 2.23352 15.8621C1.88576 15.1429 1.92821 14.3351 2.34617 13.6628L8.39192 3.93289C8.76743 3.32833 9.33396 3 10.0001 3C10.6646 3 11.2327 3.33007 11.6066 3.93289L17.654 13.6628C18.072 14.3351 18.1128 15.1429 17.7667 15.8621C17.4189 16.5831 16.7871 17 16.0458 17H3.95434ZM10.0147 11.5C9.46245 11.5 9.01473 11.0523 9.01473 10.5V6.50002C9.01473 5.94773 9.46245 5.50002 10.0147 5.50002C10.567 5.50002 11.0147 5.94773 11.0147 6.50002V10.5C11.0147 11.0523 10.567 11.5 10.0147 11.5ZM10.0147 15C9.46245 15 9.01473 14.5523 9.01473 14C9.01473 13.4477 9.46245 13 10.0147 13C10.567 13 11.0147 13.4477 11.0147 14C11.0147 14.5523 10.567 15 10.0147 15Z"
          fill="#FF4A3D"
        />
      </svg>
      <div class="price__banner-left_body">
        <p v-if="type === 'warning'" class="price__banner-main_head">Poor Reporting health</p>
        <p v-if="type === 'critical'" class="price__banner-main_head">
          Urgent: Negative reporting health
        </p>
        <p v-if="type === 'warning'" class="price__banner-sub_head">
          Based on your current plan, after <span class="bold">$50,000</span> you won’t see
          additional revenue or click data. Upgrade now to not lose any data.
        </p>
        <p v-if="type === 'critical'" class="price__banner-sub_head">
          70% of revenue and click data is not available with your current plan. Upgrade to
          <span class="bold">instantly</span> get access to all missing data.
        </p>
      </div>
    </div>
    <div class="price__banner-right">
      <div class="price__banner-button" :class="{ red: type === 'critical' }">
        <p class="price__banner-button_text">Upgrade Now</p>
      </div>
      <div v-if="type === 'warning'" class="close_button">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M7.79289 7.79289C8.18342 7.40237 8.81658 7.40237 9.20711 7.79289L16.2071 14.7929C16.5976 15.1834 16.5976 15.8166 16.2071 16.2071C15.8166 16.5976 15.1834 16.5976 14.7929 16.2071L7.79289 9.20711C7.40237 8.81658 7.40237 8.18342 7.79289 7.79289Z"
            fill="#449FF4"
          />
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M16.2071 7.79289C16.5976 8.18342 16.5976 8.81658 16.2071 9.20711L9.20711 16.2071C8.81658 16.5976 8.18342 16.5976 7.79289 16.2071C7.40237 15.8166 7.40237 15.1834 7.79289 14.7929L14.7929 7.79289C15.1834 7.40237 15.8166 7.40237 16.2071 7.79289Z"
            fill="#449FF4"
          />
        </svg>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  props: {
    type: String
  }
})
</script>

<style scoped>
.price__banner-wrapper {
  display: flex;
  width: calc(100% - 24px);
  padding: 12px;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #ffe944;
  background: #fffcd9;
}

.price__banner-wrapper.red {
  border-bottom-color: #ff4a3d;
  background: #ffe7d8;
}

.price__banner-left {
  display: flex;
  align-items: center;
  gap: 12px;
}

.price__banner-left_body {
  display: flex;
  min-width: 625px;
  flex-direction: column;
  align-items: flex-start;
  gap: 4px;
}

.price__banner-main_head {
  color: #7a0b28;
  font-family: Montserrat;
  font-size: 14px;
  font-style: normal;
  font-weight: 700;
  line-height: 18px; /* 128.571% */
  padding: 0;
  margin: 0;
}

.price__banner-sub_head {
  color: #7a0b28;
  font-family: Montserrat;
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 20px; /* 142.857% */
  padding: 0;
  margin: 0;
}

.price__banner-sub_head .bold {
  font-weight: 700;
}

.price__banner-right {
  display: flex;
  align-items: center;
  gap: 12px;
}

.price__banner-button {
  display: flex;
  width: 171px;
  padding: 6px 16px;
  justify-content: center;
  align-items: center;
  gap: 8px;
  border-radius: 10px;
  background: #449ff4;
}

.price__banner-button.red {
  background: #ff4a3d;
}

.price__banner-button_text {
  color: #ffffff;
  font-family: Montserrat;
  font-size: 13px;
  font-style: normal;
  font-weight: 600;
  line-height: 18px; /* 138.462% */
  padding: 0;
  margin: 0;
}
</style>
