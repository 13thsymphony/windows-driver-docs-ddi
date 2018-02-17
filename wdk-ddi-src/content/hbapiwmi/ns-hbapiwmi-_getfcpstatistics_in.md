---
UID: NS:hbapiwmi._GetFCPStatistics_IN
title: "_GetFCPStatistics_IN"
author: windows-driver-content
description: The GetFCPStatistics_IN structure is used to deliver input parameter data to the GetFCPStatistics WMI method.
old-location: storage\getfcpstatistics_in.htm
old-project: storage
ms.assetid: f6cb4532-fc66-45e7-a779-0981465d69fc
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: hbapiwmi/GetFCPStatistics_IN, PGetFCPStatistics_IN structure pointer [Storage Devices], *PGetFCPStatistics_IN, structs-Fibre_409be852-67ff-45c4-bce1-291076c1a70b.xml, GetFCPStatistics_IN, GetFCPStatistics_IN structure [Storage Devices], hbapiwmi/PGetFCPStatistics_IN, storage.getfcpstatistics_in, _GetFCPStatistics_IN, PGetFCPStatistics_IN
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbapiwmi.h
apiname:
-	GetFCPStatistics_IN
product: Windows
targetos: Windows
req.typenames: GetFCPStatistics_IN, *PGetFCPStatistics_IN
---

# _GetFCPStatistics_IN structure
The GetFCPStatistics_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554939">GetFCPStatistics</a> WMI method.

## Syntax
````
typedef struct _GetFCPStatistics_IN {
  HBAScsiID ScsiId;
} GetFCPStatistics_IN, *PGetFCPStatistics_IN;
````

## Members


`ScsiId`

Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_hbascsiid.md">HBAScsiID</a> that uniquely identifies a logical unit and the bus and HBA that the logical unit is connected to.

## Remarks
The WMI tool suite generates a declaration of the GetFCPStatistics_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="..\hbapiwmi\ns-hbapiwmi-_hbascsiid.md">HBAScsiID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554939">GetFCPStatistics</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetFCPStatistics_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>