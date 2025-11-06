# Developer Lightspeed on Red Hat Developer Hub

This repository documents the configuration needed to enable Developer Lightspeed for Red Hat Developer Hub (RHDH) v1.7.

Refer to the official Red Hat documentation here:  
https://docs.redhat.com/en/documentation/red_hat_developer_hub/1.7/html-single/interacting_with_red_hat_developer_lightspeed_for_red_hat_developer_hub/index

## Overview

Developer Lightspeed adds AI assisted capabilities within RHDH.  
This repository includes configuration files, sample CRs and step by step setup instructions.

## Prerequisites

• RHDH version 1.7  
• OpenShift or another compatible Kubernetes cluster  
• Permission to modify Backstage ConfigMaps or the Backstage custom resource  
• A running LLM endpoint that supports the OpenAI API  
• The LLM model name that the endpoint exposes  
• An access token for the LLM endpoint

## Configuration Steps

1. Install the Lightspeed plugin modules compatible with RHDH 1.7  
2. Enable the Lightspeed plugins in the app-config or in the Backstage custom resource  
3. Configure the backend with the LLM endpoint, model name and token  
4. Apply the ConfigMaps and CRs, then restart the RHDH pods so changes take effect  
5. Verify that Lightspeed appears in the UI and test a basic workflow

## Repo Structure

• config folder contains example configuration files  
• cr folder contains Backstage CR patches and deployment settings

## Testing

• Confirm that the Lightspeed menu appears in the RHDH interface  
• Run a Lightspeed workflow and check that it completes successfully  
• Review backend logs for plugin load errors or connectivity issues

## Troubleshooting

• Check RHDH pod logs for errors  
• Make sure the plugin versions match the RHDH 1.7 compatibility list  
• Verify that ConfigMaps are mounted correctly  
• Confirm that the LLM endpoint URL, model name and token are available to the backend  
• Use the official documentation for additional guidance
