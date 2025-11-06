# Developer Lightspeed on Red Hat Developer Hub

This repository documents the configuration needed to enable **Developer Lightspeed** for **Red Hat Developer Hub (RHDH) v1.7**.

Refer to the official Red Hat documentation for Developer Lightspeed here:  
https://docs.redhat.com/en/documentation/red_hat_developer_hub/1.7/html-single/interacting_with_red_hat_developer_lightspeed_for_red_hat_developer_hub/index

## Overview

Developer Lightspeed adds AI-assisted capabilities within RHDH, enabling developers to work faster, smarter, and with less friction.  
This repository includes required configuration files, sample CRs, and step-by-step instructions.

## Prerequisites

• RHDH version 1.7  
• An OpenShift cluster (or compatible Kubernetes cluster) with necessary access  
• Active Red Hat subscription that covers Developer Lightspeed  
• Permissions and access to modify RHDH’s Backstage configuration (ConfigMap or Backstage custom resource)

## Configuration Steps

1. Install the Lightspeed plugin modules compatible with RHDH 1.7 (check the version matrix in the official doc).  
2. Enable the Lightspeed plugin(s) in the `app-config.yaml` or the Backstage CR manifest.  
3. Create or update the backend configuration for Developer Lightspeed (e.g. secrets, API endpoints, credentials).  
4. Apply ConfigMaps/CRs to the cluster, restart the RHDH pods or deployment to pick up the changes.  
5. Validate in the UI that Lightspeed features appear (menu entries, UI components) and test a simple workflow.

## Repo Structure

• `config/` — Example snippets for `app-config.yaml`, plugin config, etc.  
• `cr/` — Sample Kubernetes CRs or manifests relevant to enabling Lightspeed.  

## Testing

After configuration:

• Confirm the “Lightspeed” or relevant menu appears in the RHDH UI.  
• Trigger a Lightspeed-enabled workflow and ensure there are no errors in the browser console or backend logs.  
• Check the relevant pod logs in the cluster for errors or startup issues.

## Troubleshooting

If something fails:

• Check the logs of the RHDH application pods for plugin load failures.  
• Verify plugin versions match RHDH 1.7 compatibility list.  
• Check ConfigMap/CR mounts and whether they were updated correctly with the new configuration.  
• Refer to the “Interacting with Developer Lightspeed for Red Hat Developer Hub” section in the official doc for known issues.
