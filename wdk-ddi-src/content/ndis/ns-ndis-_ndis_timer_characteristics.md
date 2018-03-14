---
UID: NS:ndis._NDIS_TIMER_CHARACTERISTICS
title: "_NDIS_TIMER_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_TIMER_CHARACTERISTICS structure defines characteristics of a one-shot or periodic timer.
old-location: netvista\ndis_timer_characteristics.htm
old-project: netvista
ms.assetid: 9a62e94c-f635-4ab7-b439-b98c60ba2854
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_TIMER_CHARACTERISTICS, NDIS_TIMER_CHARACTERISTICS, NDIS_TIMER_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_TIMER_CHARACTERISTICS, PNDIS_TIMER_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_TIMER_CHARACTERISTICS, ndis/NDIS_TIMER_CHARACTERISTICS, ndis/PNDIS_TIMER_CHARACTERISTICS, ndis_timer_ref_af673f64-aa72-4767-81a0-5df465a52c81.xml, netvista.ndis_timer_characteristics"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_TIMER_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_TIMER_CHARACTERISTICS, *PNDIS_TIMER_CHARACTERISTICS
---

# _NDIS_TIMER_CHARACTERISTICS structure
The NDIS_TIMER_CHARACTERISTICS structure defines characteristics of a one-shot or periodic
  timer.

## Syntax
````
typedef struct _NDIS_TIMER_CHARACTERISTICS {
  NDIS_OBJECT_HEADER   Header;
  ULONG                AllocationTag;
  PNDIS_TIMER_FUNCTION TimerFunction;
  PVOID                FunctionContext;
} NDIS_TIMER_CHARACTERISTICS, *PNDIS_TIMER_CHARACTERISTICS;
````

## Members


`AllocationTag`

A string that is delimited by single quotation marks and contains up to four characters, usually
     specified in reversed order. You must provide this tag. NDIS uses this tag when it allocates memory for
     the timer.

`FunctionContext`

A pointer to a driver-allocated context area. NDIS passes this pointer to the 
     <i>NetTimerCallback</i> function when a timer fires.

`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_TIMER_CHARACTERISTICS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_TIMER_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_TIMER_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_TIMER_CHARACTERISTICS_REVISION_1.

`TimerFunction`

A pointer to an entry point for a 
     <a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a> function. NDIS calls
     this function when a timer fires.

## Remarks
To allocate and initialize a timer object, NDIS drivers call the 
    <a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">NdisAllocateTimerObject</a> function
    and provide an NDIS_TIMER_CHARACTERISTICS structure. The timer does not start until the driver calls the 
    <a href="..\ndis\nf-ndis-ndissettimerobject.md">NdisSetTimerObject</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">NdisAllocateTimerObject</a>



<a href="..\ndis\nf-ndis-ndissettimerobject.md">NdisSetTimerObject</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TIMER_CHARACTERISTICS structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>