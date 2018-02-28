---
UID: NC:ufxclient.EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT
title: EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT
author: windows-driver-content
description: The client driver's implementation to initiate proprietary charger detection.
old-location: buses\evt_ufx_device_detect_proprietary_charger.htm
old-project: usbref
ms.assetid: A3396CC8-153E-401A-BAD6-18FEE4D14EE5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER, EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT, EvtDeviceProprietaryChargerDetect, EvtUfxDeviceDetectProprietaryCharger, EvtUfxDeviceDetectProprietaryCharger callback function [Buses], PFN_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT, PFN_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT callback function pointer [Buses], buses.evt_ufx_device_detect_proprietary_charger, ufxclient/EvtUfxDeviceDetectProprietaryCharger
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ufxclient.h
api_name:
-	PFN_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---


# EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT callback function
The client driver's implementation to initiate proprietary charger detection.

## Syntax

```
EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT EvtUfxDeviceProprietaryChargerDetect;

void EvtUfxDeviceProprietaryChargerDetect(

)
{...}
```

## Parameters

This function has no parameters.

## Return Value

This callback function does not return a value.

## Remarks

<i>EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER</i> is an optional event callback. The client driver is required to implement this event callback only if it supports proprietary charger detection. The driver indicates its support in the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a> call by setting <b>PdcpSupported</b> to TRUE in <a href="..\ufxbase\ns-ufxbase-_ufx_device_capabilities.md">UFX_DEVICE_CAPABILITIES</a>. If the client driver does not support the functionality, the <b>EvtDeviceProprietaryChargerDetect</b>, <b>EvtDeviceProprietaryChargerSetProperty</b>, and <b>EvtDeviceProprietaryChargerReset</b>
members of the <a href="..\ufxclient\ns-ufxclient-_ufx_device_callbacks.md">UFX_DEVICE_CALLBACKS</a> structure must be set to NULL in   <b>UfxDeviceCreate</b>.   

The client driver indicates completion of this event by calling the <a href="..\ufxclient\nf-ufxclient-ufxdeviceproprietarychargerdetectcomplete.md">UfxDeviceProprietaryChargerDetectComplete</a> method.

The client driver sends a request to the lower filter driver to determine if a proprietary charger is present. In response, the filter driver provides a GUID for each charger type it supports, and a list of that charger’s properties.  If a specific charger is configurable, the filter driver also provides a list of supported PropertyIDs and their possible values to configure the charger.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ufxclient.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ufxclient\nf-ufxclient-ufxdeviceproprietarychargerdetectcomplete.md">UfxDeviceProprietaryChargerDetectComplete</a>



<a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>