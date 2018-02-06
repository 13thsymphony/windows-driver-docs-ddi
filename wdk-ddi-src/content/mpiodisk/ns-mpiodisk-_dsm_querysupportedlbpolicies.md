---
UID: NS:mpiodisk._DSM_QuerySupportedLBPolicies
title: "_DSM_QuerySupportedLBPolicies"
author: windows-driver-content
description: The DSM_QuerySupportedLBPolicies structure is used to query the list of load balance policies that are supported on the LUN.
old-location: storage\dsm_querysupportedlbpolicies.htm
old-project: storage
ms.assetid: c9c04601-783a-454d-a80e-be8aa5df519a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: DSM_QuerySupportedLBPolicies structure [Storage Devices], _DSM_QuerySupportedLBPolicies, mpiodisk/PDSM_QuerySupportedLBPolicies, PDSM_QuerySupportedLBPolicies structure pointer [Storage Devices], mpiodisk/DSM_QuerySupportedLBPolicies, structs-scsibus_44692da4-cfd1-4492-94b5-1f601fa53fd0.xml, DSM_QuerySupportedLBPolicies, storage.dsm_querysupportedlbpolicies, PDSM_QuerySupportedLBPolicies, *PDSM_QuerySupportedLBPolicies
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiodisk.h
req.include-header: Mpiowmi.h
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
-	mpiodisk.h
apiname:
-	DSM_QuerySupportedLBPolicies
product: Windows
targetos: Windows
req.typenames: DSM_QuerySupportedLBPolicies, *PDSM_QuerySupportedLBPolicies
---

# _DSM_QuerySupportedLBPolicies structure
The DSM_QuerySupportedLBPolicies structure is used to query the list of load balance policies that are supported on the LUN.

## Syntax
````
typedef struct _DSM_QuerySupportedLBPolicies {
  ULONG                   SupportedLBPoliciesCount;
  ULONG                   Reserved;
  DSM_Load_Balance_Policy Supported_LB_Policies[1];
} DSM_QuerySupportedLBPolicies, *PDSM_QuerySupportedLBPolicies;
````

## Members


`Reserved`

Should be zero.

`Supported_LB_Policies`

An array of DSM_Load_Balance_Policy structures, one for each of the supported load balance policies. The number of array elements will be the same as <i>SupportedLBPoliciesCount</i>. Each element of the array lists only the supported load balance policy type.

`SupportedLBPoliciesCount`

An unsigned 32-bitfield that returns the number of policies that are supported for the LUN by the controlling DSM.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mpiodisk.h (include Mpiowmi.h) |