# Bindplane Self Monitoring
### Learn how to set up and ingest Bindplane self monitoring metrics to track collector health, pipeline anomalies and more. 

## 1. Adding Bindplane Collector as a Source

1. Navigate into your Configuration. On the left side, add a new Source.
   <img width="1702" height="1026" alt="image" src="https://github.com/user-attachments/assets/1a43df7d-9b2c-49dc-9f55-8262194d57c0" />


2. Select Bindplane Agent as the source type. Select both metrics and logs telemetry types then save the Source configuration. 
   <img width="1707" height="1196" alt="image" src="https://github.com/user-attachments/assets/d722c36f-ad23-4dbf-a757-5e38f805f0d0" />

## 2. Link Bindplane Agent Source to Dynatrace
**For both Logs and Metrics pipelines**, click the + on the Bindplane agent source and link it to your Dynatrace destination.
  <img width="1599" height="1114" alt="image" src="https://github.com/user-attachments/assets/5ac6618f-f011-4ceb-bde6-030e858e93ea" />


## 3. Adding necessary Processor
Bindplane self monitoring metrics are **cumulative data type**, but Dynatrace does not support this data type. In order to convert these to a Dynatrace supported data type, we need to add a processor to this stream. 

1. Click on the processor to the right of the Bindplane Agent source. Then, click the Add Processor button. Select "Custom" processor. 
<img width="1708" height="1197" alt="image" src="https://github.com/user-attachments/assets/1810a63d-83a5-41e4-b1e8-4661e1ec84a2" />



2. In the Custom Processor, be sure to select both Metrics and Logs. Then in the Configuration box, add `cumulativetodelta: {}` and save your configuration.
<img width="1706" height="1199" alt="image" src="https://github.com/user-attachments/assets/b9ed6d58-1a58-45bc-b754-2b48ac918791" />

## 4. Apply Changes

Now that we have the Bindplane Agent added as a source linked to Dynatrace with a processsor to convert the data types, we need to push these changes out to our collector. Click "Start Rollout" to apply these changes. 
<img width="1635" height="1184" alt="image" src="https://github.com/user-attachments/assets/3ef424bb-c097-488e-9ed6-6b6a2c84e6b9" />

## 5. Visualize Bindplane Self Monitoring Metrics in Dynatrace

Everything is now configured in Bindplane to collect self monitoring metrics and logs and are sending them to Dynatrace. Let's now create a dashboard to track the health of our Bindplane collectors. Navigate to your Dynatrace environment and to the Dashboards app. 

1. Download the Dynatrace Dashboard JSON from Github under the Dashboards folder.

2. Upload this dashboard to your Dynatrace environment.

3. Refresh your dashboard to view your Bindplane Collector health!
   <img width="1712" height="1199" alt="image" src="https://github.com/user-attachments/assets/136aebde-3a4b-4527-9cba-51129c366d85" />


   







