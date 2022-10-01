<template>
  <button class="arrow-button">
    <svg width="40rem" height="32rem" viewBox="0 0 40 32" fill="none" xmlns="http://www.w3.org/2000/svg">
      <g clip-path="url(#clip0_66_361)">
      <g filter="url(#filter0_d_66_361)">
      <path d="M5 14.5C4.17157 14.5 3.5 15.1716 3.5 16C3.5 16.8284 4.17157 17.5 5 17.5V14.5ZM35 16L35.937 17.1713C36.2929 16.8866 36.5 16.4557 36.5 16C36.5 15.5443 36.2929 15.1133 35.937 14.8287L35 16ZM27.6037 8.16202C26.9568 7.64451 26.0129 7.74939 25.4954 8.39629C24.9778 9.04318 25.0827 9.98712 25.7296 10.5046L27.6037 8.16202ZM25.7296 21.4954C25.0827 22.0129 24.9778 22.9568 25.4954 23.6037C26.0129 24.2506 26.9568 24.3555 27.6037 23.838L25.7296 21.4954ZM5 17.5H35V14.5H5V17.5ZM35.937 14.8287L27.6037 8.16202L25.7296 10.5046L34.063 17.1713L35.937 14.8287ZM34.063 14.8287L25.7296 21.4954L27.6037 23.838L35.937 17.1713L34.063 14.8287Z" fill="white"/>
      </g>
      </g>
      <defs>
      <filter id="filter0_d_66_361" x="-0.5" y="7.83327" width="41" height="24.3335" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
      <feFlood flood-opacity="0" result="BackgroundImageFix"/>
      <feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/>
      <feOffset dy="4"/>
      <feGaussianBlur stdDeviation="2"/>
      <feComposite in2="hardAlpha" operator="out"/>
      <feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.25 0"/>
      <feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_66_361"/>
      <feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_66_361" result="shape"/>
      </filter>
      <clipPath id="clip0_66_361">
      <rect width="40" height="32" fill="white"/>
      </clipPath>
      </defs>
    </svg>
  </button>
</template>

<style scoped lang="scss">
@import "../../static/scss/_vars.scss";

  .arrow-button {
    width: 70rem;
    height: 70rem;
    background: $main-color;
    border-radius: 50%;
    box-shadow: 0 4rem 4rem rgba(0, 0, 0, 0.25), inset 0 0 6rem rgba(0, 0, 0, 0.25);
  }
</style>
