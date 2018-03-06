---
UID: NS:hbapiwmi._SendRNID_OUT
title: "_SendRNID_OUT"
author: windows-driver-content
description: The SendRNID_OUT structure is used to report the output parameter data of the SendRNID WMI method to the WMI client.
old-location: storage\sendrnid_out.htm
old-project: storage
ms.assetid: 80f264f6-51cb-4125-832b-603ed8417d32
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSendRNID_OUT, PSendRNID_OUT, PSendRNID_OUT structure pointer [Storage Devices], SendRNID_OUT, SendRNID_OUT structure [Storage Devices], _SendRNID_OUT, hbapiwmi/PSendRNID_OUT, hbapiwmi/SendRNID_OUT, storage.sendrnid_out, structs-Fibre_fb365ea2-b9ff-4108-af6c-48c2d812eac3.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
-	hbapiwmi.h
api_name:
-	SendRNID_OUT
product: Windows
targetos: Windows
req.typenames: SendRNID_OUT, *PSendRNID_OUT
---

# _SendRNID_OUT structure
The SendRNID_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565459">SendRNID</a> WMI method to the WMI client.

## Syntax
````
typedef struct _SendRNID_OUT {
  ULONG HBAStatus;
  ULONG ResponseBufferCount;
  UCHAR ResponseBuffer[1];
} SendRNID_OUT, *PSendRNID_OUT;
````

## Members


`HBAStatus`

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.

`ResponseBuffer`

Contains the results of the RNID command.

`ResponseBufferCount`

Contains the size in bytes of the results of the request node identification data (RNID) command.

## Remarks
The WMI tool suite generates a declaration of the SendRNID_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565459">SendRNID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendRNID_OUT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>