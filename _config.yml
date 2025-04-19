<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>B2Ka.github.io</title>

  <!-- Google Tag Manager -->
  <script>
    (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
    new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
    j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
    'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
    })(window,document,'script','dataLayer','GTM-NGQFVCWC');
  </script>
  <!-- End Google Tag Manager -->

  <!-- Read and push URL params into GTM data layer -->
  <script>
    (function () {
      const urlParams = new URLSearchParams(window.location.search);
      const key = urlParams.get("key");
      const value = urlParams.get("value");
      window.dataLayer = window.dataLayer || [];
      if (key && value) {
        let data = {};
        data[key] = value;
        window.dataLayer.push(data);
      }
    })();
  </script>

  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
    }
    button {
      padding: 10px 20px;
      background-color: #0055ff;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }
    button:hover {
      background-color: #003bb3;
    }
  </style>
</head>

<body>
  <!-- Google Tag Manager (noscript) -->
  <noscript>
    <iframe src="https://www.googletagmanager.com/ns.html?id=GTM-NGQFVCWC"
    height="0" width="0" style="display:none;visibility:hidden"></iframe>
  </noscript>
  <!-- End Google Tag Manager (noscript) -->

  <h1>B2Ka.github.io</h1>
  <h2>My Impact Test</h2>

  <p>This test demonstrates GTM and API integration using query string parameters.</p>

  <button onclick="sendAPIRequest()">Send GET Request</button>

  <script>
    function sendAPIRequest() {
      const dataLayer = window.dataLayer || [];
      let latestData = {};
      for (let i = dataLayer.length - 1; i >= 0; i--) {
        const entry = dataLayer[i];
        if (typeof entry === "object" && !entry["gtm.start"]) {
          latestData = entry;
          break;
        }
      }

      const [key, value] = Object.entries(latestData)[0] || [];
      if (!key || !value) {
        console.log("No valid key-value found in dataLayer.");
        return;
      }

      const apiUrl = `https://httpbin.org/get?${encodeURIComponent(key)}=${encodeURIComponent(value)}`;
      console.log("Sending GET request to:", apiUrl);

      fetch(apiUrl)
        .then((response) => response.json())
        .then((data) => {
          console.log("API Response:", data);
        })
        .catch((error) => {
          console.error("API Request Failed:", error);
        });
    }
  </script>
</body>
</html>
