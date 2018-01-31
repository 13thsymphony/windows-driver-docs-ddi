---
UID : NF:nfccx.NfcCxUnregisterSequenceHandler
title : NfcCxUnregisterSequenceHandler function
author : windows-driver-content
description : Called by the client driver during device shutdown to unregister for the previously registered sequence handler callback.
old-location : nfpdrivers\_nfccxunregistersequencehandler.htm
old-project : nfpdrivers
ms.assetid : 689BF221-22CA-43B4-A5EB-ECE0B78F520B
ms.author : windowsdriverdev
ms.date : 12/18/2017
ms.keywords : nfccx/NfcCxUnregisterSequenceHandler, nfpdrivers._nfccxunregistersequencehandler, NfcCxUnregisterSequenceHandler, NfcCxUnregisterSequenceHandler method [Near-Field Proximity Drivers]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : nfccx.h
req.include-header : Ncidef.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : None supported
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Nfccxstub.lib
req.dll : NfcCx.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNFC_CX_TRANSPORT_TYPE, NFC_CX_TRANSPORT_TYPE"
---


# NfcCxUnregisterSequenceHandler function
Called by the client driver during device shutdown to unregister for the previously registered sequence handler callback.

## Syntax

````
NTSTATUS NfcCxUnregisterSequenceHandler(
   WDFDEVICE       Device,
   NFC_CX_SEQUENCE Sequence
);
````

## Parameters

`Device`

A handle to a framework device object.

`Sequence`

An <a href="..\nfccx\ne-nfccx-_nfc_cx_sequence.md">NFC_CX_SEQUENCE</a>-typed enumerator.


## Return Value

If the operation succeeds, the function returns STATUS_SUCCESS.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | nfccx.h (include Ncidef.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NfcCxUnregisterSequenceHandler method%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>