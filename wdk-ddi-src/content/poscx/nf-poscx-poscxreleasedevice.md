---
UID: NF:poscx.PosCxReleaseDevice
title: PosCxReleaseDevice function
author: windows-driver-content
description: PosCxReleaseDevice is called to release a device that was previously claimed with PosCxClaimDevice. Once the device is released, the next pending claim requester is promoted.
old-location: pos\poscxreleasedevice.htm
old-project: pos
ms.assetid: 9615915C-B729-4702-BF41-D5068B43A729
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PosCxReleaseDevice, PosCxReleaseDevice function, pos.poscxreleasedevice, poscx/PosCxReleaseDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
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
-	poscx.h
api_name:
-	PosCxReleaseDevice
product:
- Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---


# PosCxReleaseDevice function
PosCxReleaseDevice is called to release a device that was previously claimed with
      <a href="https://msdn.microsoft.com/library/windows/hardware/mt593119">PosCxClaimDevice</a>.
      Once the device is released, the next pending claim requester is promoted.

## Syntax

```
NTSTATUS PosCxReleaseDevice(
  WDFDEVICE     device,
  WDFFILEOBJECT fileObject
);
```

## Parameters

`device`

A handle to a framework device object that represents the device.

`fileObject`

A handle to a framework file object that identifies the caller.


## Return Value

Possible return values are:

<table>
<tr>
<td><b>STATUS_SUCCESS</b></td>
<td>The device was successfully released.</td>
</tr>
<tr>
<td><b>STATUS_ACCESS_DENIED</b></td>
<td>The calling thread is not the owner of the device.</td>
</tr>
<tr>
<td><b>STATUS_DEVICE_NOT_READY</b></td>
<td>The PosCx library was not successfully initialized.</td>
</tr>
<tr>
<td><b>STATUS_INVALID_PARAMETER </b></td>
<td>The specified <i>fileObject</i> is invalid.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | poscx.h (include Poscx.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt593119">PosCxClaimDevice</a>