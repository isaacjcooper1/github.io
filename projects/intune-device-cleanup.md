
---
layout: corporate
title: Intune Device Cleanup Automation | Case Study
permalink: /projects/intune-device-cleanup/
---

<section class="section">
  <div class="container narrow">
    <h1>Intune Device Cleanup Automation</h1>
    <p class="lead">PowerShell job to identify and remove stale device objects across Intune and Entra ID, reducing noise and improving reporting fidelity.</p>

    <div class="key-facts">
      <div><strong>Stack:</strong> PowerShell, Microsoft Graph API, Intune</div>
      <div><strong>Role:</strong> Design, implementation, and documentation</div>
      <div><strong>Repo:</strong> <a href="https://github.com/your-github-username/intune-device-cleanup" target="_blank" rel="noopener">GitHub →</a></div>
    </div>

    <h2>Problem</h2>
    <p>Stale device objects accumulate due to re-enrollments, hardware changes, or decommissioning without proper offboarding. This inflates device counts and undermines compliance and patch reporting.</p>

    <h2>Approach</h2>
    <ul>
      <li>Enumerate devices via Graph API with last check-in timestamps.</li>
      <li>Apply policy thresholds (e.g., no check-in for 30/60/90 days) with exceptions.</li>
      <li>Soft-delete workflow with approval window; hard delete after retention.</li>
      <li>Audit logging to storage with daily summary email/Teams webhook.</li>
    </ul>

    <h2>Results</h2>
    <ul>
      <li>Reduced stale objects by ~65% within the first month.</li>
      <li>Improved accuracy of compliance/patch dashboards.</li>
      <li>Saved ~4-6 engineer hours per week previously spent on manual cleanup.</li>
    </ul>

    <h2>Snippet</h2>
    <pre class="code"><code># Example: Get Intune devices not checked in for 60 days
# (Pseudo-logic; replace with your production script)
$threshold = (Get-Date).AddDays(-60)
$devices = Invoke-GraphRequest -Uri   'https://graph.microsoft.com/beta/deviceManagement/managedDevices?$select=deviceName,lastSyncDateTime,azureADDeviceId'   -Method GET
$stale = $devices | Where-Object { $_.lastSyncDateTime -lt $threshold }
$stale | ForEach-Object { Write-Host "Would remove: $($_.deviceName)" }
</code></pre>

    <h2>What I'd Improve Next</h2>
    <ul>
      <li>Service principal token handling with managed identity.</li>
      <li>Parameterized thresholds per device group.</li>
      <li>Visualization of trends in Power BI.</li>
    </ul>

    <p><a class="btn btn-primary" href="{ '/' | relative_url }#projects">← Back to Projects</a></p>
  </div>
</section>
