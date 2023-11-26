<template>
  <div class="price__modal-wrapper">
    <div class="price__inner-modal">
      <div class="price__inner-header">
        <p class="light_text">Current Plan: <span class="bold_text">Up to $50k/month</span></p>
        <div class="close_button">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="25"
            viewBox="0 0 24 25"
            fill="none"
          >
            <path
              d="M19 5.5L5 19.5M19 19.5L5 5.5"
              stroke="#727279"
              stroke-width="2"
              stroke-linecap="round"
            />
          </svg>
        </div>
      </div>
      <div class="price__inner-content">
        <div class="price_content-face">{{ type === 'warning' ? '😅' : '🤦‍♂️' }}</div>
        <h5 v-if="type === 'warning'" class="price_content-header">
          Friendly warning... you may be losing data soon!
        </h5>
        <h5 v-if="type === 'critical'" class="price_content-header">
          You’re missing 20% of your revenue and click data
        </h5>
        <div class="price_content-progress-wrapper">
          <p v-if="type === 'warning'" class="progress_header">
            Warning - Your data will soon be maxed
          </p>
          <p v-if="type === 'critical'" class="progress_header">
            Your data is not fully being reported
          </p>
          <div class="progress">
            <div class="progress_group">
              <div class="progress_background" :class="{ red: type === 'critical' }">
                <div class="progress_indicator"></div>
              </div>
            </div>
          </div>
          <div class="progress_bottom">
            <p v-if="type === 'warning'" class="progress_left_text">60% of data used this month.</p>
            <div v-if="type === 'critical'" class="critical_info">
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
              Revenue: <span class="progress_right_text_bold">48k</span>
            </p>
          </div>
        </div>
        <div class="price__inner-bottom">
          <p v-if="type === 'warning'" class="price__inner-long_text">
            Beyond $50,000 your revenue and click data will not be available. To avoid missing data,
            we highly recommend upgrading to the right tier.
          </p>
          <p v-if="type === 'critical'" class="price__inner-long_text">
            We’re still tracking your data, but you’ll need to upgrade to access all your data.
            <span class="bold">
              Without all data you might make inaccurate or negative decisions!
            </span>
          </p>
          <a v-if="type === 'warning'" href="#" class="price__inner-learn_more"
            >Learn More about Plans</a
          >
        </div>
      </div>
      <div class="price__modal-footer">
        <div class="footer_buttons" :class="{ center: type === 'critical' }">
          <div v-if="type === 'warning'" class="footer_button">
            <p class="button_text">Remind me Later</p>
          </div>
          <div class="footer_button green" :class="{ center: type === 'critical' }">
            <p class="button_text white">Upgrade to Pro</p>
          </div>
        </div>
        <p v-if="type === 'critical'" class="footer_text">
          Get access to all your missing data instantly
        </p>
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
.price__modal-wrapper {
  position: fixed;
  width: 100vw;
  height: 100vh;
  background: #484848;
  opacity: 0.8;
  display: flex;
  justify-content: center;
  align-items: center;
}

.price__inner-modal {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 584px;
  /* height: 688px; */
  border-radius: 10px;
  background: #ffffff;
  box-shadow:
    0px 32px 41px -23px rgba(24, 24, 28, 0.07),
    0px 2px 6px 0px rgba(24, 24, 28, 0.06);
}

.price__inner-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px 24px;
}

.light_text {
  color: #222124;
  font-family: Montserrat;
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: 24px; /* 150% */
  padding: 0;
  margin: 0;
}

.bold_text {
  font-weight: 600;
  line-height: 20px;
}

.price__inner-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 64px 24px;
  gap: 24px;
}

.price_content-face {
  color: #34404b;
  text-align: center;
  font-family: Montserrat;
  font-size: 56px;
  font-style: normal;
  font-weight: 700;
  line-height: 64px; /* 114.286% */
}

.price_content-header {
  max-width: 407px;
  width: 100%;
  color: #34404b;
  text-align: center;
  font-family: Montserrat;
  font-size: 28px;
  font-style: normal;
  font-weight: 700;
  line-height: 32px; /* 114.286% */
  padding: 0;
  margin: 0;
}

.price_content-progress-wrapper {
  display: flex;
  width: 432px;
  padding: 20px 16px;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  gap: 8px;
  border-radius: 8px;
  border: 1px solid #e6e7e8;
  background: #fff;
  box-shadow: 0px 6px 12px 0px rgba(26, 40, 53, 0.05);
}

.progress_header {
  color: #5a5c60;
  font-family: Montserrat;
  font-size: 14px;
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

.price__inner-bottom {
  display: flex;
  flex-direction: column;
  gap: 12px;
  max-width: 518px;
  width: 100%;
  text-align: center;
}

.price__inner-long_text {
  color: #000;
  text-align: center;
  font-family: Montserrat;
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: 24px; /* 150% */
  padding: 0 16px;
  margin: 0;
}

.price__inner-long_text .bold {
  font-weight: 700;
}

.price__inner-learn_more {
  color: #000;
  text-align: center;
  font-family: Montserrat;
  font-size: 16px;
  font-style: normal;
  font-weight: 400;
  line-height: 24px; /* 150% */
  text-decoration-line: underline;
  padding: 0;
  margin: 0;
}

.price__modal-footer {
  display: flex;
  padding: 20px 24px;
  flex-direction: column;
  /* align-items: flex-end; */
  gap: 8px;
  align-self: stretch;
  border-top: 1px solid #efefef;
}

.footer_buttons {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  align-self: stretch;
}

.footer_buttons.center {
  display: flex;
  width: 100%;
  justify-content: center;
  align-items: center;
}

.footer_button {
  display: flex;
  padding: 10px 20px;
  justify-content: center;
  align-items: center;
  gap: 8px;
  border-radius: 10px;
  border: 1px solid #4d5861;
}

.footer_button.center {
  background: #00936f;
  width: 292px;
}

.footer_button.green {
  background: #00936f;
  border: 1px solid #00936f;
}

.button_text {
  color: #4d5861;
  font-family: Montserrat;
  font-size: 14px;
  font-style: normal;
  font-weight: 600;
  line-height: 18px; /* 128.571% */
  padding: 0;
  margin: 0;
}

.button_text.white {
  color: #ffffff;
}

.footer_text {
  color: #1a2835;
  text-align: center;
  font-family: Montserrat;
  font-size: 12px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  padding: 0;
  margin: 0;
}
</style>
