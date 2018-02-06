---
UID: NC:gpioclx.GPIO_CLIENT_PREPARE_CONTROLLER
title: GPIO_CLIENT_PREPARE_CONTROLLER
author: windows-driver-content
description: The CLIENT_PrepareController event callback function performs any operations that are needed to make the general-purpose I/O (GPIO) controller ready to be accessed by the GPIO controller driver.
old-location: gpio\client_preparecontroller.htm
old-project: GPIO
ms.assetid: FAB86862-C0A1-4FC1-A80F-44F235B9B37D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO.client_preparecontroller, CLIENT_PrepareController callback function [Parallel Ports], CLIENT_PrepareController, GPIO_CLIENT_PREPARE_CONTROLLER, GPIO_CLIENT_PREPARE_CONTROLLER, gpioclx/CLIENT_PrepareController
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: gpioclx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Gpioclx.h
apiname:
-	CLIENT_PrepareController
product: Windows
targetos: Windows
req.typenames: "*PGNSS_V2UPL_NI_INFO, GNSS_V2UPL_NI_INFO"
---


# GPIO_CLIENT_PREPARE_CONTROLLER function
The <i>CLIENT_PrepareController</i> event callback function performs any operations that are needed to make the general-purpose I/O (GPIO) controller ready to be accessed by the GPIO controller driver.

## Syntax

```
GPIO_CLIENT_PREPARE_CONTROLLER GpioClientPrepareController;

NTSTATUS GpioClientPrepareController(
  WDFDEVICE Device,
  PVOID Context,
  WDFCMRESLIST ResourcesRaw,
  WDFCMRESLIST ResourcesTranslated
)
{...}
```

## Parameters

`Device`

A WDFDEVICE handle to the framework device object that represents the GPIO controller.

`Context`

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.

`ResourcesRaw`

A WDFCMRESLIST handle to a collection of framework resource objects. This collection identifies the raw (bus-relative) hardware resources that the Plug and Play (PnP) manager has assigned to the GPIO controller device.

`ResourcesTranslated`

A WDFCMRESLIST handle to a collection of framework resource objects. This collection identifies the translated (system-physical) hardware resources that the PnP manager has assigned to the GPIO controller device.


## Return Value

The <i>CLIENT_PrepareController</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## Remarks

This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function to initialize the hardware resources that the GPIO controller driver needs so that it can access the GPIO controller device.

The <i>ResourcesRaw</i> and <i>ResourcesTranslated</i> parameters are handles to lists of raw and translated resources. These lists describe hardware resources that the PnP manager has assigned to the GPIO controller device that is specified by the <i>Device</i> parameter. For more information, see <a href="https://msdn.microsoft.com/dfc1376d-7a1a-421c-82ae-e183cac77ec8">Raw and Translated Resources</a>.

During the <i>CLIENT_PrepareController</i> callback, the GPIO controller driver can acquire the hardware resources that it requires from the <i>ResourcesRaw</i> or <i>ResourcesTranslated</i> list. If the GPIO controller device is memory-mapped, the driver should map the bus-relative memory address range or ranges that are assigned to the device's hardware registers to system virtual addresses. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554399">Mapping Bus-Relative Addresses to Virtual Addresses</a>.

If the GPIO controller is not memory-mapped, the driver's hardware resources contain a connection ID instead of a memory range. The driver uses this ID to open a logical connection to the GPIO controller, and sends I/O requests through this connection to access the controller's registers.

GpioClx connects to (and later disconnects from) any interrupt resource that the PnP manager assigns to the GPIO controller. If GpioClx receives such an interrupt resource, it does not remove this interrupt resource from the resource lists that it passes to the <i>CLIENT_PrepareController</i> callback function. However, the GPIO controller driver should not try to connect to (or later disconnect from) any interrupt resource that it finds in these lists.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439411">CLIENT_ReleaseController</a> event callback function performs operations that are needed when the GPIO controller device is no longer accessible. During this callback, the GPIO controller driver should release any hardware resources that it acquired during the previous <i>CLIENT_PrepareController</i> callback.

To register your driver's <i>CLIENT_PrepareController</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_PrepareController</i> function pointer.

Although the <i>CLIENT_PrepareController</i> callback function is called at IRQL = PASSIVE_LEVEL, you should not make this function pageable. The <i>CLIENT_PrepareController</i> callback is in the critical timing path for restoring power to the devices in the hardware platform and, for performance reasons, it should not be delayed by page faults.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Target Platform** | Desktop |
| **Header** | gpioclx.h |
| **IRQL** | Called at PASSIVE_LEVEL. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439411">CLIENT_ReleaseController</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_PrepareController callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>