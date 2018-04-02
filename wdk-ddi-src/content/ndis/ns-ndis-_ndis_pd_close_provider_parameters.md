---
UID: NS:ndis._NDIS_PD_CLOSE_PROVIDER_PARAMETERS
title: "_NDIS_PD_CLOSE_PROVIDER_PARAMETERS"
author: windows-driver-content
description: This structure represents the parameters that are used when calling the OID_PD_CLOSE_PROVIDER OID.
old-location: netvista\ndis_pd_close_provider_parameters.htm
old-project: netvista
ms.assetid: 9C33CA12-E725-4634-A1EC-0A919987BA6E
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_PD_CLOSE_PROVIDER_PARAMETERS, NDIS_PD_CLOSE_PROVIDER_PARAMETERS structure [Network Drivers Starting with Windows Vista], _NDIS_PD_CLOSE_PROVIDER_PARAMETERS, ndis/NDIS_PD_CLOSE_PROVIDER_PARAMETERS, netvista.ndis_pd_close_provider_parameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ndis.h
api_name:
-	NDIS_PD_CLOSE_PROVIDER_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_PD_CLOSE_PROVIDER_PARAMETERS
---

# _NDIS_PD_CLOSE_PROVIDER_PARAMETERS structure
This structure represents the parameters that are used when calling the <a href="https://msdn.microsoft.com/library/windows/hardware/dn931851">OID_PD_CLOSE_PROVIDER</a> OID.

## Syntax
```
typedef struct _NDIS_PD_CLOSE_PROVIDER_PARAMETERS {
  NDIS_OBJECT_HEADER      Header;
  ULONG                   Flags;
  NDIS_PD_PROVIDER_HANDLE ProviderHandle;
} NDIS_PD_CLOSE_PROVIDER_PARAMETERS;
```

## Members


`Header`

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_CLOSE_PROVIDER_PARAMETERS</b> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_CLOSE_PROVIDER_PARAMETERS_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_CLOSE_PROVIDER_PARAMETERS_REVISION_1</b></li>
</ul>

`Flags`

This member is reserved and must be set to 0.

`ProviderHandle`

A provider handle that identifies the PD-capable miniport driver's provider object.

## Remarks
This structure must be aligned on an 8-byte boundary.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | ndis.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn931851">OID_PD_CLOSE_PROVIDER</a>