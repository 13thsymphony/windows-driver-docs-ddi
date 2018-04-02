---
UID: NF:nfccx.NfcCxDeviceDeinitialize
title: NfcCxDeviceDeinitialize function
author: windows-driver-content
description: Called by the client driver after a WDF device has been created during the AddDevice routine.
old-location: nfpdrivers\_nfccxdevicedeinitialize.htm
old-project: nfpdrivers
ms.assetid: 1E1AC024-D628-4E31-80EF-8E929B8449FE
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: NfcCxDeviceDeinitialize, NfcCxDeviceDeinitialize method [Near-Field Proximity Drivers], nfccx/NfcCxDeviceDeinitialize, nfpdrivers._nfccxdevicedeinitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Nfccsstub.lib
req.dll: NfcCx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NfcCx.dll
api_name:
-	NfcCxDeviceDeinitialize
product:
- Windows
targetos: Windows
req.typenames: NFC_CX_TRANSPORT_TYPE, *PNFC_CX_TRANSPORT_TYPE
---


# NfcCxDeviceDeinitialize function
Called by the client driver after a WDF device has been created during the AddDevice routine.

## Syntax

```
NTSTATUS NfcCxDeviceDeinitialize(
  WDFDEVICE Device
);
```

## Parameters

`Device`

A handle to a framework device object.


## Return Value

If the operation succeeds, the function returns STATUS_SUCCESS.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 None supported |
| **Target Platform** | Windows |
| **Header** | nfccx.h (include Ncidef.h) |
| **Library** | Nfccsstub.lib |
| **DLL** | NfcCx.dll |

## See Also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>