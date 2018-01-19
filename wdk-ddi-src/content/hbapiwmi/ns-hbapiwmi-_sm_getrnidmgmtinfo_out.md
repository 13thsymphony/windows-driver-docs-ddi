---
UID : NS:hbapiwmi._SM_GetRNIDMgmtInfo_OUT
title : _SM_GetRNIDMgmtInfo_OUT
author : windows-driver-content
description : The SM_GetRNIDMgmtInfo_OUT structure is used to receive output parameters from the SM_GetRNIDMgmtInfo method.
old-location : storage\sm_getrnidmgmtinfo_out.htm
old-project : storage
ms.assetid : e12bd494-4d2a-44a9-95dc-0bc78fa73a97
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _SM_GetRNIDMgmtInfo_OUT, *PSM_GetRNIDMgmtInfo_OUT, SM_GetRNIDMgmtInfo_OUT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : hbapiwmi.h
req.include-header : Hbapiwmi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SM_GetRNIDMgmtInfo_OUT
req.alt-loc : hbapiwmi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PSM_GetRNIDMgmtInfo_OUT, SM_GetRNIDMgmtInfo_OUT"
---

# _SM_GetRNIDMgmtInfo_OUT structure
The SM_GetRNIDMgmtInfo_OUT structure is used to receive output parameters from the SM_GetRNIDMgmtInfo method.

## Syntax
````
typedef struct _SM_GetRNIDMgmtInfo_OUT {
  ULONG          HBAStatus;
  HBAFC3MgmtInfo MgmtInfo;
} SM_GetRNIDMgmtInfo_OUT, *PSM_GetRNIDMgmtInfo_OUT;
````

## Members

        
            `HBAStatus`

            The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.
        
            `MgmtInfo`

            A structure of type HBAFC3MgmtInfo that holds FC3 management information. The FC3 management information is used to configure the fibre channel adapter.

    ## Remarks
        The WMI tool suite generates a declaration of the SM_GetRNIDMgmtInfo_OUTstructure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |