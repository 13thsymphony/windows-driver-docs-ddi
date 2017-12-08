# Hardware notifications

Overview of the Hardware notifications technology.

To develop Hardware notifications, you need these headers:

 * [hwnclx.h](..\hwnclx\index.md)

For the programming guide, see [Hardware notifications](https://docs.microsoft.com/en-us/windows-hardware/drivers/gpiobtn).

## Functions

| Title   | Description   |
| ---- |:---- |
| [HwNProcessAddDevicePostDeviceCreate function](..\hwnclx\nf-hwnclx-hwnprocessadddevicepostdevicecreate.md) | Creates I/O queues. It should be called after the client driver’s EVT_WDF_DRIVER_DEVICE_ADD callback function is invoked and the device object has been created. |
| [HwNProcessAddDevicePreDeviceCreate function](..\hwnclx\nf-hwnclx-hwnprocessadddevicepredevicecreate.md) | Supplies the device prepare/release and entry/exit callbacks to the Windows Driver Foundation (WDF) for transitioning the device into different states. |
| [HwNRegisterClient function](..\hwnclx\nf-hwnclx-hwnregisterclient.md) | Registers the hardware notification client driver and its callback functions with the class extension. |
| [HwNUnregisterClient function](..\hwnclx\nf-hwnclx-hwnunregisterclient.md) | Unregisters the hardware notification client driver and its callback functions with the class extension. This function should be invoked when the client driver is unloaded. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [HWN_CLIENT_GET_STATE callback](..\hwnclx\nc-hwnclx-hwn-client-get-state.md) | Implemented by the client driver to get hardware notification component state. It is invoked when a user requests status information. |
| [HWN_CLIENT_INITIALIZE_DEVICE callback](..\hwnclx\nc-hwnclx-hwn-client-initialize-device.md) | Implemented by the client driver and is invoked as a result of a call to EVT_WDF_DEVICE_PREPARE_HARDWARE. |
| [HWN_CLIENT_QUERY_DEVICE_INFORMATION callback](..\hwnclx\nc-hwnclx-hwn-client-query-device-information.md) | Implemented by the client driver to retrieve hardware notification component attributes. |
| [HWN_CLIENT_SET_STATE callback](..\hwnclx\nc-hwnclx-hwn-client-set-state.md) | Implemented by the client driver to set hardware notification component state. It is invoked when a user wants to change the state of a driver. |
| [HWN_CLIENT_START_DEVICE callback](..\hwnclx\nc-hwnclx-hwn-client-start-device.md) | Implemented by the client driver to start the hardware notification component. It is invoked as a result of a call to EVT_WDF_DEVICE_D0_ENTRY. |
| [HWN_CLIENT_STOP_DEVICE callback](..\hwnclx\nc-hwnclx-hwn-client-stop-device.md) | Implemented by the client driver TO start the hardware notification component. It is invoked as a result of a call to EVT_WDF_DEVICE_D0_EXIT. |
| [HWN_CLIENT_UNINITIALIZE_DEVICE callback](..\hwnclx\nc-hwnclx-hwn-client-uninitialize-device.md) | Implemented by the client driver and invoked as invoked as a result of a call to EVT_WDF_DEVICE_RELEASE_HARDWARE. This callback function uninitializes the hardware notification component. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [CLIENT_DEVICE_INFORMATION structure](..\hwnclx\ns-hwnclx--client-device-information.md) | The CLIENT_DEVICE_INFORMATION structure is used by the hardware notification callback HWN_CLIENT_QUERY_DEVICE_INFORMATION to return the total number of hardware notifications that the client device driver provides. |
| [HWN_CLIENT_REGISTRATION_PACKET structure](..\hwnclx\ns-hwnclx--hwn-client-registration-packet.md) | Hardware Notification client driver registration packet that is passed to the class extension when a client driver is registered. Contains version information and client driver callback functions. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [HWN_CLX_EXPORT_INDEX enumeration](..\hwnclx\ne-hwnclx--hwn-clx-export-index.md) | Defines the position for each of the Hardware Notification exports in the export table. |
