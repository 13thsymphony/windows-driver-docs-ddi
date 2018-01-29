---
UID : NC:ufxclient.EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD
title : EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD
author : windows-driver-content
description : The client driver's implementation to create a default control endpoint.
old-location : buses\evt_ufx_device_default_endpoint_add.htm
old-project : usbref
ms.assetid : 37AF38A2-F761-4DBC-A7E7-FC4BDA544A31
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : buses.evt_ufx_device_default_endpoint_add, EvtUfxDeviceDefaultEndpointAdd callback function [Buses], EvtUfxDeviceDefaultEndpointAdd, EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD, EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD, ufxclient/EvtUfxDeviceDefaultEndpointAdd, PFN_UFX_DEVICE_DEFAULT_ENDPOINT_ADD callback function pointer [Buses], PFN_UFX_DEVICE_DEFAULT_ENDPOINT_ADD
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ufxclient.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT"
req.product : Windows 10 or later.
---


# EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD function
The client driver's implementation to create a default control endpoint.

## Syntax

```
EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD EvtUfxDeviceDefaultEndpointAdd;

void EvtUfxDeviceDefaultEndpointAdd(
  UFXDEVICE ,
  USHORT ,
  PUFXENDPOINT_INIT 
)
{...}
```

## Parameters

``



``



``




## Return Value

This callback function does not return a value.

## Remarks

The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</i> implementation with the USB function class extension (UFX) by calling the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a> method.

To create the endpoint the client driver is expected to initialize the attributes of the endpoint’s transfer and command queues, and then call <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a> to create the endpoint.  After the default control endpoint is created, UFX is ready to process setup packets and other control transfer packets from host.  

The client driver indicates completion of this event by calling the <a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ufxclient.h |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>

<a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>