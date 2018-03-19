---
UID: NF:mcd.ChangerPerformDiagnostics
title: ChangerPerformDiagnostics function
author: windows-driver-content
description: ChangerPerformDiagnostics performs diagnostic tests on the changer device.
old-location: storage\changerperformdiagnostics.htm
old-project: storage
ms.assetid: 87767b2b-8ca3-4d19-8719-673562246a41
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ChangerPerformDiagnostics, ChangerPerformDiagnostics function [Storage Devices], chgrmini_dd38573a-a1cc-4b7b-abdf-0a200ba11d88.xml, mcd/ChangerPerformDiagnostics, storage.changerperformdiagnostics
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mcd.h
api_name:
-	ChangerPerformDiagnostics
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---


# ChangerPerformDiagnostics function
<b>ChangerPerformDiagnostics</b> performs diagnostic tests on the changer device.

## Syntax

````
NTSTATUS ChangerPerformDiagnostics(
  _In_  PDEVICE_OBJECT                    DeviceObject,
  _Out_ PWMI_CHANGER_PROBLEM_DEVICE_ERROR ChangerDeviceError
);
````

## Parameters

`DeviceObject`

Pointer to the device object that represents the changer.

`changerDeviceError`

TBD


## Return Value

<b>ChangerPerformDiagnostics</b> returns the status returned by the system port driver or one of the following values:
      

STATUS_SUCCESS

STATUS_INSUFFICIENT_RESOURCES

STATUS_BUFFER_TOO_SMALL

## Remarks

<b>ChangerPerformDiagnostics</b> routine performs diagnostic tests on the changer device, and reports the problem to the caller. The kind of tests performed depends on the diagnostics support provided by the device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | mcd.h (include Mcd.h, Ntddchgr.h) |

## See Also

<a href="..\wmidata\ns-wmidata-_wmi_changer_problem_device_error.md">WMI_CHANGER_PROBLEM_DEVICE_ERROR</a>



<a href="..\ntddchgr\ne-ntddchgr-_changer_device_problem_type.md">CHANGER_DEVICE_PROBLEM_TYPE</a>