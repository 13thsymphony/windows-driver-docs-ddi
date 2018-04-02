---
UID: NF:nfccx.NfcCxRegisterSequenceHandler
title: NfcCxRegisterSequenceHandler function
author: windows-driver-content
description: Called by the client driver during initialization to register for handling specific sequences.
old-location: nfpdrivers\_nfccxregistersequencehandler.htm
old-project: nfpdrivers
ms.assetid: 30957475-D02B-434D-9FAB-BBCD5732DCA5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: NfcCxRegisterSequenceHandler, NfcCxRegisterSequenceHandler method [Near-Field Proximity Drivers], nfccx/NfcCxRegisterSequenceHandler, nfpdrivers._nfccxregistersequencehandler
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
req.lib: Nfccxstub.lib
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
-	NfcCxRegisterSequenceHandler
product:
- Windows
targetos: Windows
req.typenames: NFC_CX_TRANSPORT_TYPE, *PNFC_CX_TRANSPORT_TYPE
---


# NfcCxRegisterSequenceHandler function
Called by the client driver during initialization to register for handling specific sequences.

## Syntax

```
NTSTATUS NfcCxRegisterSequenceHandler(
  WDFDEVICE                   Device,
  NFC_CX_SEQUENCE             Sequence,
  PFN_NFC_CX_SEQUENCE_HANDLER EvtNfcCxSequenceHandler
);
```

## Parameters

`Device`

A handle to a framework device object.

`Sequence`

An <a href="https://msdn.microsoft.com/library/windows/hardware/dn905563">NFC_CX_SEQUENCE</a>-typed enumerator.

`EvtNfcCxSequenceHandler`

A pointer to an <a href="https://msdn.microsoft.com/6EB96A37-06B9-4655-AD69-375EE770F4DF">EvtNfcCxSequenceHandler</a> callback function.


## Return Value

If the operation succeeds, the function returns STATUS_SUCCESS.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 None supported |
| **Target Platform** | Windows |
| **Header** | nfccx.h (include Ncidef.h) |
| **Library** | Nfccxstub.lib |
| **DLL** | NfcCx.dll |

## See Also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>