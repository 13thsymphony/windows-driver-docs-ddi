---
UID: NS:hbapiwmi._SM_SetRNIDMgmtInfo_OUT
title: "_SM_SetRNIDMgmtInfo_OUT"
author: windows-driver-content
description: The SM_SetRNIDMgmtInfo_OUT structure is used to receive output parameters from the SM_SetRNIDMgmtInfo method.
old-location: storage\sm_setrnidmgmtinfo_out.htm
old-project: storage
ms.assetid: 30bb4e82-3a51-4d58-87aa-2e1545a9244f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSM_SetRNIDMgmtInfo_OUT structure pointer [Storage Devices], structs-Fibre_c416e571-7970-4856-937a-a8bd546d8d3d.xml, hbapiwmi/SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT, hbapiwmi/PSM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT structure [Storage Devices], storage.sm_setrnidmgmtinfo_out, PSM_SetRNIDMgmtInfo_OUT, _SM_SetRNIDMgmtInfo_OUT
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
-	SM_SetRNIDMgmtInfo_OUT
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---

# _SM_SetRNIDMgmtInfo_OUT structure
The SM_SetRNIDMgmtInfo_OUT structure is used to receive output parameters from the SM_SetRNIDMgmtInfo method.

## Syntax
````
typedef struct _SM_SetRNIDMgmtInfo_OUT {
  ULONG HBAStatus;
} SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT;
````

## Members


`HBAStatus`

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.

## Remarks
The WMI tool suite generates a declaration of the SM_SetRNIDMgmtInfo_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |