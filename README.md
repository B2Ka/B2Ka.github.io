# B2Ka.github.io
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>A Meaningful Page Title</title>

  <!-- Push query parameters to dataLayer -->
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

  <!-- Google Tag Manager -->
  <script>
    (function (w, d, s, l, i) {
      w[l] = w[l] || [];
      w[l].push({ "gtm.start": new Date().getTime(), event: "gtm.js" });
      var f = d.getElementsByTagName(s)[0],
        j = d.createElement(s),
        dl = l != "dataLayer" ? "&l=" + l : "";
      j.async = true;
      j.src = "https://www.googletagmanager.com/gtm.js?id=" + i + dl;
      f.parentNode.insertBefore(j, f);
    })(window, document, "script", "dataLayer", "GTM-NGQFVCWC");
  </script>
  <!-- End Google Tag Manager -->

  <!-- Function to send the API request -->
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

      const apiUrl = `https://httpbin.org/get?${encodeURIComponent(
        key
      )}=${encodeURIComponent(value)}`;
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
</head>
<body>
  <!-- Google Tag Manager (noscript) -->
  <noscript>
    <iframe
      src="https://www.googletagmanager.com/ns.html?id=GTM-NGQFVCWC"
      height="0"
      width="0"
      style="display: none; visibility: hidden"
    ></iframe>
  </noscript>
  <!-- End Google Tag Manager (noscript) -->

  <h1># B2Ka.github.io</h1>
  <h2># My Impact Test</h2>

  <p>The content of the body element is displayed in the browser window.</p>
  <p>The content of the title element is displayed in the browser tab, in favorites and in search-engine results.</p>

  <!-- The button -->
  <button onclick="sendAPIRequest()">Send GET Request</button>
</body>
</html>
