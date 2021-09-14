This experiment covers a MicroSoft Azure tutorial to get started with IoT with Raspberry Pi Web simulator :

Below is a gist of process for a very first experiment with Azure IoT Hub and Raspberry Pi Web simulator

1. Create an IoT hub.

2. Register a device for Pi in your IoT hub.

3. Run a sample application on Pi to send simulated sensor data to your IoT hub.

**Raspberry Pi Web simulator part**

There are three areas in the web simulator.

Assembly area - The default circuit is that a Pi connects with a BME280 sensor and an LED. The area is locked in preview version so currently you cannot do customization.

Coding area - An online code editor for you to code with Raspberry Pi. The default sample application helps to collect sensor data from BME280 sensor and sends to your Azure IoT Hub. The application is fully compatible with real Pi devices.

Integrated console window - It shows the output of your code. 

    Run - Run the application in the coding area.

    Reset - Reset the coding area to the default sample application.

**Procedure briefings:**

create IoT Hub : https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started#create-an-iot-hub

Register new device in IoT Hub : https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started#register-a-new-device-in-the-iot-hub

Replace connection String in node.js code in simulator

**Visualize with VS Code - Azure IoT Hub:**

1. Install Azure IoT Hub Extension for VS code - https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.azure-iot-tools

2. In Explorer view of VS Code, expand Azure IoT Hub Devices section in the bottom left corner.

3. Click Select IoT Hub in context menu.

4. A pop-up will show in the bottom right corner to let you sign in to Azure for the first time.

5. After you sign in, your Azure Subscription list will be shown, then select Azure Subscription and IoT Hub.

The device list will be shown in Azure IoT Hub Devices tab in a few seconds.

**Monitor device-to-cloud messages:**

To monitor messages that are sent from your device to your IoT hub, follow these steps:

Right-click your device and select Start Monitoring Built-in Event Endpoint.

The monitored messages will be shown in OUTPUT > Azure IoT Hub view.

To stop monitoring, right-click the OUTPUT view and select Stop Monitoring Built-in Event Endpoint.

**Send cloud-to-device messages:**

To send a message from your IoT hub to your device, follow these steps:

Right-click your device and select Send C2D Message to Device.

Enter the message in input box.

Results will be shown in OUTPUT > Azure IoT Hub view.
