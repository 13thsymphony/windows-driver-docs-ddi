---
UID: NS:hbapiwmi._SendRPS_OUT
title: "_SendRPS_OUT"
author: windows-driver-content
description: The SendRPS_OUT structure is used to report the output parameter data of the SendRPS WMI method to the WMI client.
old-location: storage\sendrps_out.htm
old-project: storage
ms.assetid: 5d243704-7424-4738-b122-6b9467eb5916
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSendRPS_OUT, SendRPS_OUT, SendRPS_OUT structure [Storage Devices], _SendRPS_OUT, hbapiwmi/SendRPS_OUT, storage.sendrps_out, structs-Fibre_0c81817b-666f-4b2b-8ae2-2342894d7c46.xml"
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
-	SendRPS_OUT
product: Windows
targetos: Windows
req.typenames: SendRPS_OUT, *PSendRPS_OUT
---

# _SendRPS_OUT structure
The SendRPS_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565505">SendRPS</a> WMI method to the WMI client.

## Syntax
````
struct SendRPS_OUT {
  ULONG HBAStatus;
  ULONG TotalRspBufferSize;
  ULONG ActualRspBufferSize;
  UCHAR RspBuffer[1];
};
````

## Members


`ActualRspBufferSize`

Contains the size in bytes of the data that was actually retrieved.

`HBAStatus`

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.

`RspBuffer`

Contains the results of the RPS command.

`TotalRspBufferSize`

Contains the size in bytes of the results of the RPS command.

## Remarks
The WMI tool suite generates a declaration of the SendRPS_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565505">SendRPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendRPS_OUT structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>