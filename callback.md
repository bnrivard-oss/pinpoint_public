---
title: QuickBooks authorization — Claude Pnpt MCP
---

# QuickBooks authorization

<div id="result">
  <p>Waiting for authorization details…</p>
</div>

<script>
(function () {
  var params = new URLSearchParams(window.location.search);
  var box = document.getElementById("result");

  function esc(s) {
    return String(s).replace(/[&<>"]/g, function (c) {
      return { "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;" }[c];
    });
  }

  var error = params.get("error");
  if (error) {
    box.innerHTML =
      "<h2>Authorization was not granted</h2><p>" +
      esc(params.get("error_description") || error) +
      "</p><p>Close this tab and run <code>npm run login</code> again.</p>";
    return;
  }

  var code = params.get("code");
  var realmId = params.get("realmId");
  var state = params.get("state");

  if (!code || !realmId) {
    box.innerHTML =
      "<h2>Nothing to show</h2><p>Open this page by completing the QuickBooks " +
      "authorization flow — it is not meant to be visited directly.</p>";
    return;
  }

  box.innerHTML =
    "<p><strong>Authorization received.</strong> Copy the two values below into " +
    "the terminal where <code>npm run login</code> is waiting.</p>" +
    "<h2>Authorization code</h2>" +
    "<pre id=\"code\" style=\"white-space:pre-wrap;word-break:break-all;padding:.75rem;border:1px solid #ccc;border-radius:4px\">" +
    esc(code) + "</pre>" +
    "<h2>Realm ID (company ID)</h2>" +
    "<pre id=\"realm\" style=\"padding:.75rem;border:1px solid #ccc;border-radius:4px\">" +
    esc(realmId) + "</pre>" +
    (state ? "<p style=\"color:#666\">State: <code>" + esc(state) + "</code></p>" : "") +
    "<p style=\"color:#666\">The authorization code expires in a few minutes, so paste it " +
    "promptly. Nothing on this page is transmitted anywhere — it is read from the URL in " +
    "your browser and displayed here only.</p>";
})();
</script>

<noscript>
This page needs JavaScript to read the authorization values from the URL. Alternatively,
copy the <code>code</code> and <code>realmId</code> parameters directly out of your
browser's address bar.
</noscript>
