---
UID: NS:hbapiwmi._SM_SendCTPassThru_OUT
title: "_SM_SendCTPassThru_OUT"
author: windows-driver-content
description: The SM_SendCTPassThru_OUT structure is used to receive output parameters from the SM_SendCTPassThru method.
old-location: storage\sm_sendctpassthru_out.htm
old-project: storage
ms.assetid: df1869d1-83ed-4574-85c2-89fb2b78d177
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSM_SendCTPassThru_OUT, PSM_SendCTPassThru_OUT, PSM_SendCTPassThru_OUT structure pointer [Storage Devices], SM_SendCTPassThru_OUT, SM_SendCTPassThru_OUT structure [Storage Devices], _SM_SendCTPassThru_OUT, hbapiwmi/PSM_SendCTPassThru_OUT, hbapiwmi/SM_SendCTPassThru_OUT, storage.sm_sendctpassthru_out, structs-Fibre_a3193f45-e459-49a2-a0ab-71bbde4ea1ef.xml"
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
-	SM_SendCTPassThru_OUT
product:
- Windows
targetos: Windows
req.typenames: SM_SendCTPassThru_OUT, *PSM_SendCTPassThru_OUT
---

# _SM_SendCTPassThru_OUT structure
The SM_SendCTPassThru_OUT structure is used to receive output parameters from the SM_SendCTPassThru method.

## Syntax
```
typedef struct _SM_SendCTPassThru_OUT {
  ULONG HBAStatus;
  ULONG TotalRespBufferSize;
  ULONG OutRespBufferSize;
  UCHAR RespBuffer[1];
} SM_SendCTPassThru_OUT, *PSM_SendCTPassThru_OUT;
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
The WMI tool suite generates a declaration of the SM_SendCTPassThru_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |