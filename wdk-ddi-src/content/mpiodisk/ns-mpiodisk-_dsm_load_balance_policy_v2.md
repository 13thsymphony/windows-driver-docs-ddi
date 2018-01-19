---
UID : NS:mpiodisk._DSM_Load_Balance_Policy_V2
title : _DSM_Load_Balance_Policy_V2
author : windows-driver-content
description : The DSM_Load_Balance_Policy_V2 structure is used to represent a load balance policy that is applied to a LUN.
old-location : storage\dsm_load_balance_policy_v2.htm
old-project : storage
ms.assetid : b1522320-110c-46dc-be50-df7c05d61351
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _DSM_Load_Balance_Policy_V2, *PDSM_Load_Balance_Policy_V2, DSM_Load_Balance_Policy_V2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : mpiodisk.h
req.include-header : Mpiowmi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DSM_Load_Balance_Policy_V2
req.alt-loc : mpiodisk.h
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
req.typenames : "*PDSM_Load_Balance_Policy_V2, DSM_Load_Balance_Policy_V2"
---

# _DSM_Load_Balance_Policy_V2 structure
The DSM_Load_Balance_Policy_V2 structure is used to represent a load balance policy that is applied to a LUN. It is similar to the DSM_Load_Balance_Policy structure, except that it uses the MPIO_DSM_Path_V2 structure to capture and expose path information.

## Syntax
````
typedef struct _DSM_Load_Balance_Policy_V2 {
  ULONG            Version;
  ULONG            LoadBalancePolicy;
  ULONG            DSMPathCount;
  ULONG            Reserved;
  MPIO_DSM_Path_V2 DSM_Paths[1];
} DSM_Load_Balance_Policy_V2, *PDSM_Load_Balance_Policy_V2;
````

## Members

        
            `DSM_Paths`

            An array of MPIO_DSM_Path_V2 structures that represent path attributes for each of the LUN's instances.
        
            `DSMPathCount`

            An unsigned 32-bitfield that represents the number of paths that expose the LUN's instances.
        
            `LoadBalancePolicy`

            An unsigned 32-bitfield that represents the load balance policy type that is currently being applied to the LUN if the LUN is being queried, or the new policy to apply to the LUN if the LUN is being set.
        
            `Reserved`

            Should be zero.
        
            `Version`

            The version of WMI class supported. Set to 2.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | mpiodisk.h (include Mpiowmi.h) |