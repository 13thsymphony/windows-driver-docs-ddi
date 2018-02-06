---
UID: NS:nfccx._NFC_CX_HARDWARE_EVENT
title: "_NFC_CX_HARDWARE_EVENT"
author: windows-driver-content
description: The NFC_CX_HARDWARE_EVENT structure is an input parameter to NfcCxHardwareEvent.
old-location: nfpdrivers\nfc_cx_hardware_event.htm
old-project: nfpdrivers
ms.assetid: FC7566C0-95FD-450C-897E-C57870386512
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: nfpdrivers.nfc_cx_hardware_event, NFC_CX_HARDWARE_EVENT structure [Near-Field Proximity Drivers], NFC_CX_HARDWARE_EVENT, nfccx/PNFC_CX_HARDWARE_EVENT, PNFC_CX_HARDWARE_EVENT structure pointer [Near-Field Proximity Drivers], PNFC_CX_HARDWARE_EVENT, *PNFC_CX_HARDWARE_EVENT, nfccx/NFC_CX_HARDWARE_EVENT, _NFC_CX_HARDWARE_EVENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	nfccx.h
apiname:
-	NFC_CX_HARDWARE_EVENT
product: Windows
targetos: Windows
req.typenames: "*PNFC_CX_HARDWARE_EVENT, NFC_CX_HARDWARE_EVENT"
---

# _NFC_CX_HARDWARE_EVENT structure
The NFC_CX_HARDWARE_EVENT structure is an input parameter to <a href="..\nfccx\nf-nfccx-nfccxhardwareevent.md">NfcCxHardwareEvent.</a>

## Syntax
````
typedef struct _NFC_CX_HARDWARE_EVENT {
  NTSTATUS           HardwareStatus;
  NFC_CX_HOST_ACTION HostAction;
} NFC_CX_HARDWARE_EVENT, *PNFC_CX_HARDWARE_EVENT;
````

## Members


`HardwareStatus`

An <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS </a> value.

`HostAction`

An <a href="..\nfccx\ne-nfccx-_nfc_cx_host_action.md">NFC_CX_HOST_ACTION</a>-typed enumerator.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | nfccx.h (include Ncidef.h) |

## See Also

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_HARDWARE_EVENT structure%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>