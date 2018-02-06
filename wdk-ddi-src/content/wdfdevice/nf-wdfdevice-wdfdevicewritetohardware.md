---
UID: NF:wdfdevice.WdfDeviceWriteToHardware
title: WdfDeviceWriteToHardware function
author: windows-driver-content
description: The WdfDeviceWriteToHardware method is used internally by the framework. Do not use.
old-location: wdf\wdfdevicewritetohardware.htm
old-project: wdf
ms.assetid: D79F1D98-E326-4401-86B8-2C3D071DF27C
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFDEVICEWRITETOHARDWARE, WdfDeviceWriteToHardware method, wdfdevice/WdfDeviceWriteToHardware, WdfDeviceWriteToHardware, wdfhwaccess/WdfDeviceWriteToHardware, wdf.wdfdevicewritetohardware
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDeviceWriteToHardware
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceWriteToHardware function
The <b>WdfDeviceWriteToHardware</b> method is used internally by the framework. Do not use.

Instead, use the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265662">WDF Register/Port Access Functions</a>.

## Syntax

````
void WdfDeviceWriteToHardware(
  _In_     WDFDEVICE                       Device,
  _In_     WDF_DEVICE_HWACCESS_TARGET_TYPE Type,
  _In_     WDF_DEVICE_HWACCESS_TARGET_SIZE Size,
  _In_     PVOID                           TargetAddress,
  _In_     SIZE_T                          Value,
  _In_opt_ PVOID                           Buffer,
  _In_opt_ ULONG                           Count
);
````

## Parameters

`Device`



`Type`



`Size`



`TargetAddress`



`Value`



`Buffer`



`Count`




## Return Value

This method does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.11 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/55FBE72C-E74E-4116-9602-6D491592350F">WriteToHardware</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceWriteToHardware method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>