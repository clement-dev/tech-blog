<template>
  <div class="theme-toggle">
    <div id="wrapper">
      <div id="left">
        <p v-if="mode === 'dark'" @click="toggleMode('sepia')">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="20"
            height="20"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
            class="feather feather-moon"
          >
            <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"></path>
          </svg>
        </p>
        <p v-if="mode === 'sepia'" @click="toggleMode('light')">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="20"
            height="20"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
            class="feather feather-coffee"
          >
            <path d="M18 8h1a4 4 0 0 1 0 8h-1"></path>
            <path d="M2 8h16v9a4 4 0 0 1-4 4H6a4 4 0 0 1-4-4V8z"></path>
            <line x1="6" y1="1" x2="6" y2="4"></line>
            <line x1="10" y1="1" x2="10" y2="4"></line>
            <line x1="14" y1="1" x2="14" y2="4"></line>
          </svg>
        </p>
        <p v-if="mode === 'light'" @click="toggleMode('dark')">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="20"
            height="20"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
            class="feather feather-sun"
          >
            <circle cx="12" cy="12" r="5"></circle>
            <line x1="12" y1="1" x2="12" y2="3"></line>
            <line x1="12" y1="21" x2="12" y2="23"></line>
            <line x1="4.22" y1="4.22" x2="5.64" y2="5.64"></line>
            <line x1="18.36" y1="18.36" x2="19.78" y2="19.78"></line>
            <line x1="1" y1="12" x2="3" y2="12"></line>
            <line x1="21" y1="12" x2="23" y2="12"></line>
            <line x1="4.22" y1="19.78" x2="5.64" y2="18.36"></line>
            <line x1="18.36" y1="5.64" x2="19.78" y2="4.22"></line>
          </svg>
        </p>
      </div>
      <div id="right">
        <p v-if="typo === 'sans-serif'" @click="toggleFont('serif')">
          <svg
            width="12"
            height="100%"
            viewBox="0 0 34 56"
            version="1.1"
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            xml:space="preserve"
            xmlns:serif="http://www.serif.com/"
            fill="currentColor"
            stroke="currentColor"
          >
            <g transform="matrix(1,0,0,1,-170,-2)">
              <path
                id="text2173"
                d="M201.637,9.017L201.285,9.017C200.606,8.782 199.703,8.56 198.578,8.349C197.453,8.138 196.422,8.032 195.485,8.032C192.672,8.032 190.563,8.747 189.157,10.177C187.75,11.606 186.684,13.892 185.957,17.032L176.782,57.567L170.102,57.567L179.278,17.032C180.285,12.462 182.149,8.899 184.867,6.345C187.586,3.79 191.196,2.513 195.696,2.513C197.172,2.513 198.52,2.583 199.739,2.724C200.957,2.864 202.047,3.028 203.008,3.216L201.637,9.017Z"
                style="fill-rule: nonzero"
              />
            </g>
          </svg>
        </p>
        <p v-if="typo === 'serif'" @click="toggleFont('sans-serif')">
          <svg
            width="18"
            height="100%"
            viewBox="0 0 47 66"
            version="1.1"
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            xml:space="preserve"
            xmlns:serif="http://www.serif.com/"
            fill="currentColor"
            stroke="currentColor"
          >
            <g transform="matrix(1,0,0,1,-52,-3)">
              <path
                id="text2165"
                d="M76.409,40.026C73.62,51.042 70.55,58.6 67.198,62.702C63.847,66.803 60.425,68.854 56.933,68.854C55.667,68.854 54.554,68.526 53.593,67.87C52.632,67.214 52.152,66.37 52.152,65.339C52.152,64.471 52.48,63.786 53.136,63.282C53.792,62.778 54.484,62.526 55.21,62.526C55.843,62.526 56.382,62.719 56.827,63.106C57.273,63.493 57.495,63.956 57.495,64.495C57.495,64.987 57.202,65.514 56.616,66.077C56.335,66.335 56.195,66.546 56.195,66.71C56.195,67.178 56.593,67.413 57.39,67.413C58.89,67.413 60.384,66.774 61.872,65.497C63.361,64.219 64.486,62.544 65.247,60.469C66.009,58.395 67.152,54.393 68.675,48.464L74.792,24.663C76.48,18.171 78.988,12.985 82.316,9.106C85.644,5.227 89.159,3.288 92.863,3.288C94.363,3.288 95.698,3.71 96.87,4.553C98.042,5.397 98.628,6.405 98.628,7.577C98.628,8.327 98.37,9.007 97.855,9.616C97.339,10.225 96.636,10.53 95.745,10.53C95.019,10.53 94.427,10.319 93.97,9.897C93.513,9.475 93.284,8.971 93.284,8.385C93.284,7.964 93.472,7.448 93.847,6.839C94.081,6.44 94.198,6.112 94.198,5.854C94.198,5.151 93.613,4.8 92.441,4.8C87.683,4.8 83.827,10.647 80.874,22.342L76.409,40.026Z"
                style="fill-rule: nonzero"
              />
            </g>
          </svg>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      mode: "light",
      typo: "serif",
    };
  },
  created() {
    const htmlElement = document.documentElement;
    const mode = localStorage.getItem("theme");
    if (mode) {
      this.mode = mode;
      htmlElement.setAttribute("theme", mode);
    }
    const typo = localStorage.getItem("font");
    if (typo) {
      this.typo = typo;
      htmlElement.setAttribute("font", typo);
    }
  },
  methods: {
    toggleMode(mode) {
      this.mode = mode;
      const htmlElement = document.documentElement;
      htmlElement.setAttribute("theme", mode);
      localStorage.setItem("theme", mode);
    },
    toggleFont(typo) {
      this.typo = typo;
      const htmlElement = document.documentElement;
      htmlElement.setAttribute("font", typo);
      localStorage.setItem("font", typo);
    },
  },
};
</script>

<style lang="scss">
.theme-toggle {
  margin-top: 12px;
  svg {
    &:hover {
      color: var(--app-icon-color);
      cursor: pointer;
      transition: 0.4s ease all;
    }
  }
}
#wrapper {
  display: flex;
}

#left {
  flex: 0 0 65%;
  margin-left: 20px;
}

#right {
  flex: 1;
}
</style>