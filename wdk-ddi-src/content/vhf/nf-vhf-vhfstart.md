---
UID: NF:vhf.VhfStart
title: VhfStart function
author: windows-driver-content
description: The HID source driver calls this method to start the virtual HID device.
old-location: hid\vhfstart.htm
old-project: hid
ms.assetid: F3DA4CBB-5749-4E7D-828F-398714575173
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: VhfStart, VhfStart method [Human Input Devices], hid.vhfstart, vhf/VhfStart
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vhf.h
req.include-header: 
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
req.lib: VhfKm.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	VhfKm.lib
-	VhfKm.dll
api_name:
-	VhfStart
product: Windows
targetos: Windows
req.typenames: USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
req.product: Windows 10 or later.
---


# VhfStart function
The HID source driver calls this method to start the virtual HID device.

## Syntax

````
NTSTATUS VhfStart(
  [in] VHFHANDLE VhfHandle
);
````

## Parameters

`VhfHandle`

A handle to a virtual HID device that your HID source driver received in the previous call to <a href="..\vhf\nf-vhf-vhfcreate.md">VhfCreate</a>.


## Return Value

If the <b>VhfStart</b> call succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS </a> value.

## Remarks

Virtual HID Framework (VHF) does not invoke any callback functions implemented by the HID source driver until the source driver calls <b>VhfStart</b>. A callback can get invoked before <b>VhfStart</b> returns.  After this call succeeds, the driver can  submit reports. The HID source driver must not invoke any VHF method until after <b>VhfStart</b> returns successfully

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | vhf.h |
| **Library** | VhfKm.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |