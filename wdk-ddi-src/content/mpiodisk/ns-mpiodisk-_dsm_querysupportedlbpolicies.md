---
UID: NS:mpiodisk._DSM_QuerySupportedLBPolicies
title: _DSM_QuerySupportedLBPolicies
author: windows-driver-content
description: The DSM_QuerySupportedLBPolicies structure is used to query the list of load balance policies that are supported on the LUN.
old-location: storage\dsm_querysupportedlbpolicies.htm
old-project: storage
ms.assetid: c9c04601-783a-454d-a80e-be8aa5df519a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DSM_QuerySupportedLBPolicies, DSM_QuerySupportedLBPolicies, *PDSM_QuerySupportedLBPolicies
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
req.alt-api: DSM_QuerySupportedLBPolicies
req.alt-loc: mpiodisk.h
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
req.typenames: DSM_QuerySupportedLBPolicies, *PDSM_QuerySupportedLBPolicies
---

# _DSM_QuerySupportedLBPolicies structure



## -description
The DSM_QuerySupportedLBPolicies structure is used to query the list of load balance policies that are supported on the LUN.



## -syntax

````
typedef struct _DSM_QuerySupportedLBPolicies {
  ULONG                   SupportedLBPoliciesCount;
  ULONG                   Reserved;
  DSM_Load_Balance_Policy Supported_LB_Policies[1];
} DSM_QuerySupportedLBPolicies, *PDSM_QuerySupportedLBPolicies;
````


## -struct-fields

### -field SupportedLBPoliciesCount

An unsigned 32-bitfield that returns the number of policies that are supported for the LUN by the controlling DSM.


### -field Reserved

Should be zero.


### -field Supported_LB_Policies

An array of DSM_Load_Balance_Policy structures, one for each of the supported load balance policies. The number of array elements will be the same as <i>SupportedLBPoliciesCount</i>. Each element of the array lists only the supported load balance policy type.


## -remarks
