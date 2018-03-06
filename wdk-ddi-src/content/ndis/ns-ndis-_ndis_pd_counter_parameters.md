---
UID: NS:ndis._NDIS_PD_COUNTER_PARAMETERS
title: "_NDIS_PD_COUNTER_PARAMETERS"
author: windows-driver-content
description: This structure holds parameters for the provider counter.
old-location: netvista\ndis_pd_counter_parameters.htm
old-project: netvista
ms.assetid: 0F2AB5A3-9208-426A-ADC5-C1AD3BADFD83
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NDIS_PD_COUNTER_PARAMETERS, NDIS_PD_COUNTER_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_PD_COUNTER_PARAMETERS, PNDIS_PD_COUNTER_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PD_COUNTER_PARAMETERS, ndis/NDIS_PD_COUNTER_PARAMETERS, ndis/PNDIS_PD_COUNTER_PARAMETERS, netvista.ndis_pd_counter_parameters
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
-	NDIS_PD_COUNTER_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_PD_COUNTER_PARAMETERS
---

# _NDIS_PD_COUNTER_PARAMETERS structure
This structure holds parameters for the provider counter.

## Syntax
````
typedef struct _NDIS_PD_COUNTER_PARAMETERS {
  NDIS_OBJECT_HEADER   Header;
  ULONG                Flags;
  PCWSTR               CounterName;
  NDIS_PD_COUNTER_TYPE Type;
} NDIS_PD_COUNTER_PARAMETERS, *PNDIS_PD_COUNTER_PARAMETERS;
````

## Members


`CounterName`

This member  is ignored by the PD provider. It is used by the PD platform for publishing the counter to the Windows Performance Counter subsystem (so that the counter can be viewed using PerfMon and accessed by system APIs programmatically).

`Flags`

This member is reserved and must be set to 0.

`Header`

The <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_COUNTER_PARAMETERS</b> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_COUNTER_PARAMETERS_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_COUNTER_PARAMETERS_REVISION_1</b></li>
</ul>

`Type`

An <a href="..\ndis\ne-ndis-ndis_pd_counter_type.md">NDIS_PD_COUNTER_TYPE</a> enumeration value that specifies the counter type.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | ndis.h |

## See Also

<a href="..\ndis\nc-ndis-ndis_pd_allocate_counter.md">NdisPDAllocateCounter</a>



<a href="..\ndis\ne-ndis-ndis_pd_counter_type.md">NDIS_PD_COUNTER_TYPE</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PD_COUNTER_PARAMETERS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>