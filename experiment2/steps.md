Microsoft Power BI to visualize real-time sensor data that your Azure IoT hub receives.

1. Create a consumer group on your IoT hub.
2. Create and configure an Azure Stream Analytics job to read temperature telemetry from your consumer group and send it to Power BI.
3. Create a report of the temperature data in Power BI and share it to the web.

Note: Complete experiment 1 before starting and create a Power Bi account .

Step1:
Add a consumer group to your IoT hub :

In IoT hub, on the left pane, select Built-in endpoints. Enter a name for your new consumer group in the text box under Consumer groups.

https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-live-data-visualization-in-power-bi#add-a-consumer-group-to-your-iot-hub

Step2:

Create, configure, and run a Stream Analytics job - 
i. Create Stream Analytics Job
ii. Open the Stream Analytics job.

Under Job topology, select Inputs.

In the Inputs pane, select Add stream input, then select IoT Hub from the drop-down list. Make a note of following fields , 

IoT Hub: Select the IoT Hub you're using for this tutorial.

Endpoint: Select Messaging.

iii. Add an output to the Stream Analytics job

Under Job topology, select Outputs.

In the Outputs pane, select Add, and then select Power BI from the drop-down list.

Consumer group: Select the consumer group you created previously.

iv. Configure the query of the Stream Analytics job
Under Job topology, select Query.

Replace [YourInputAlias] with the input alias of the job.

Replace [YourOutputAlias] with the output alias of the job.

Add the following WHERE clause as the last line of the query. This line ensures that only messages with a temperature property will be forwarded to Power BI.

    WHERE temperature IS NOT NULL

v. Run the Stream Analytics job

**Power BI**

Select the workspace you used from the side menu, My Workspace.

Under the All tab or the Datasets + dataflows tab, you should see the dataset that you specified when you created the output for the Stream Analytics job.

Hover over the dataset you created, select More options menu (the three dots to the right of the dataset name), and then select Create report

Create a line chart to show real-time temperature over time.

On the Visualizations pane of the report creation page, select the line chart icon to add a line chart. Use the guides located on the sides and corners of the chart to adjust its size and position.

On the Fields pane, expand the table that you specified when you created the output for the Stream Analytics job.

Drag EventEnqueuedUtcTime to Axis on the Visualizations pane.

Drag temperature to Values.

A line chart is created. The x-axis displays date and time in the UTC time zone. The y-axis displays temperature from the sensor.

