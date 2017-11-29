# Wdfdriver.h header


This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfdriver.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_DRIVER_CONFIG_INIT function](nf-wdfdriver-wdf-driver-config-init.md) | The WDF_DRIVER_CONFIG_INIT function initializes a driver's WDF_DRIVER_CONFIG structure. |
| [WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function](nf-wdfdriver-wdf-driver-version-available-params-init.md) | The WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT function initializes a WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure. |
| [WdfDriverCreate function](nf-wdfdriver-wdfdrivercreate.md) | The WdfDriverCreate method creates a framework driver object for the calling driver. |
| [WdfDriverGetRegistryPath function](nf-wdfdriver-wdfdrivergetregistrypath.md) | The WdfDriverGetRegistryPath method retrieves the path to the driver's registry key in the registry's Services tree. |
| [WdfDriverIsVersionAvailable function](nf-wdfdriver-wdfdriverisversionavailable.md) | The WdfDriverIsVersionAvailable method returns a Boolean value that indicates whether the driver is running with a specified version of the Kernel-Mode Driver Framework library. |
| [WdfDriverOpenParametersRegistryKey function](nf-wdfdriver-wdfdriveropenparametersregistrykey.md) | The WdfDriverOpenParametersRegistryKey method opens the driver's Parameters registry key and retrieves a handle to a framework registry-key object that represents the key. |
| [WdfDriverRegisterTraceInfo function](nf-wdfdriver-wdfdriverregistertraceinfo.md) | The WdfDriverRegisterTraceInfo method is reserved for internal use only. |
| [WdfDriverRetrieveVersionString function](nf-wdfdriver-wdfdriverretrieveversionstring.md) | The WdfDriverRetrieveVersionString method retrieves a Unicode string that identifies the version of the Kernel-Mode Driver Framework that the driver is running with. |
| [WdfDriverWdmGetDriverObject function](nf-wdfdriver-wdfdriverwdmgetdriverobject.md) | The WdfDriverWdmGetDriverObject method retrieves a pointer to the Windows Driver Model (WDM) driver object that is associated with a specified framework driver object. |
| [WdfGetDriver function](nf-wdfdriver-wdfgetdriver.md) | The WdfGetDriver method returns a handle to the framework driver object that represents the calling driver. |
| [WdfWdmDriverGetWdfDriverHandle function](nf-wdfdriver-wdfwdmdrivergetwdfdriverhandle.md) | The WdfWdmDriverGetWdfDriverHandle method returns a handle to the framework driver object that is associated with a specified Windows Driver Model (WDM) driver object. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_WDF_DRIVER_DEVICE_ADD callback](nc-wdfdriver-evt-wdf-driver-device-add.md) | A driver's EvtDriverDeviceAdd event callback function performs device initialization operations when the Plug and Play (PnP) manager reports the existence of a device. |
| [EVT_WDF_DRIVER_UNLOAD callback](nc-wdfdriver-evt-wdf-driver-unload.md) | A driver's EvtDriverUnload event callback function performs operations that must take place before the driver is unloaded. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [WDF_DRIVER_CONFIG structure](ns-wdfdriver--wdf-driver-config.md) | The WDF_DRIVER_CONFIG structure is an input parameter to WdfDriverCreate. |
| [WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure](ns-wdfdriver--wdf-driver-version-available-params.md) | The WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure specifies major and minor version numbers for the Kernel-Mode Driver Framework's library. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [WDF_DRIVER_INIT_FLAGS enumeration](ne-wdfdriver--wdf-driver-init-flags.md) | The WDF_DRIVER_INIT_FLAGS enumeration specifies driver initialization flags. |
