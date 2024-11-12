<template>
  <div class="iframe-container">
    <iframe :src="url" width="100%" height="100%"></iframe>
  </div>
</template>

<script>
export default {
  data() {
    return {
      url: 'https://dfa.w3webtechnologies.co.in/boot1/', // The iframe URL
      iframeData: null,
    };
  },
  mounted() {
    // Listen for messages from iframe
    window.addEventListener('message', this.handleMessage, false);
  },
  beforeDestroy() {
    // Remove event listener on component destruction
    window.removeEventListener('message', this.handleMessage, false);
  },
  methods: {
  //   handleMessage(event) {
  //     // Ensure the message is from a trusted source
  //     if (event.origin === 'https://dfa.w3webtechnologies.co.in') {
  //       const data = event.data;

  //       // Handle the data
  //       if (data && data.type === 'data') {
  //         this.iframeData = data.content;
  //         console.log('Received data from iframe:', this.iframeData);
  //       }
  //     }
  //   },
  //     mounted() {
  //   // Listen for messages from iframe
  //   window.addEventListener('message', this.handleMessage, false);
  // },
  // beforeDestroy() {
  //   // Remove event listener on component destruction
  //   window.removeEventListener('message', this.handleMessage, false);
  // },
  },
};
</script>

<style scoped>
.iframe-container {
  width: 100%;
  height: 100vh; /* 100% of the viewport height */
  margin: 0;
  padding: 0;
}

iframe {
  border: none;
  width: 100%;
  height: 100%; /* Fill the container */
}
</style>
