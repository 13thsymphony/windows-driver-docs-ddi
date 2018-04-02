---
UID: NS:hbapiwmi._SM_SendLIRR_OUT
title: "_SM_SendLIRR_OUT"
author: windows-driver-content
description: The SM_SendLIRR_OUT structure is used to receive output parameters from the SM_SendLIRR method.
old-location: storage\sm_sendlirr_out.htm
old-project: storage
ms.assetid: 68e6ab20-b8a2-4a72-bb38-28fe4345e638
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSM_SendLIRR_OUT, PSM_SendLIRR_OUT, PSM_SendLIRR_OUT structure pointer [Storage Devices], SM_SendLIRR_OUT, SM_SendLIRR_OUT structure [Storage Devices], _SM_SendLIRR_OUT, hbapiwmi/PSM_SendLIRR_OUT, hbapiwmi/SM_SendLIRR_OUT, storage.sm_sendlirr_out, structs-Fibre_42d6f555-895e-4cb7-a2fb-8bc61025a940.xml"
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
-	SM_SendLIRR_OUT
product: Windows
targetos: Windows
req.typenames: SM_SendLIRR_OUT, *PSM_SendLIRR_OUT
---

# _SM_SendLIRR_OUT structure
The SM_SendLIRR_OUT structure is used to receive output parameters from the SM_SendLIRR method.

## Syntax
```
typedef struct _SM_SendLIRR_OUT {
  ULONG HBAStatus;
  ULONG TotalRespBufferSize;
  ULONG OutRespBufferSize;
  UCHAR RespBuffer[1];
} SM_SendLIRR_OUT, *PSM_SendLIRR_OUT;
```

## Members


`HBAStatus`

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.

`TotalRespBufferSize`

The size, in bytes, of the results common transport (CT) command.

`OutRespBufferSize`

The size, in bytes, of the data that was actually retrieved.

`RespBuffer`

The results of the common transport command.

## Remarks
The WMI tool suite generates a declaration of the SM_SendRNID_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |