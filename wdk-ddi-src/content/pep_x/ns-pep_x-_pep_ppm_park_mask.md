---
UID: NS:pep_x._PEP_PPM_PARK_MASK
title: "_PEP_PPM_PARK_MASK"
author: windows-driver-content
description: The PEP_PROCESSOR_PARK_MASK structure contains the current core parking mask.
old-location: kernel\pep_ppm_park_mask.htm
old-project: kernel
ms.assetid: 528576FD-BDB2-4772-9151-A1C855BA953E
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_PPM_PARK_MASK, PEP_PPM_PARK_MASK, PEP_PPM_PARK_MASK structure [Kernel-Mode Driver Architecture], PPEP_PPM_PARK_MASK, PPEP_PPM_PARK_MASK structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_PARK_MASK, kernel.pep_ppm_park_mask, pepfx/PEP_PPM_PARK_MASK, pepfx/PPEP_PPM_PARK_MASK"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PPM_PARK_MASK
product: Windows
targetos: Windows
req.typenames: PEP_PPM_PARK_MASK, *PPEP_PPM_PARK_MASK, PEP_PPM_PARK_MASK, *PPEP_PPM_PARK_MASK
---

# _PEP_PPM_PARK_MASK structure
The <b>PEP_PROCESSOR_PARK_MASK</b> structure contains the current core parking mask.

## Syntax
````
typedef struct _PEP_PPM_PARK_MASK {
  ULONG                                              Count;
  ULONGLONG                                          EvaluationTime;
  _Field_size_full_(Count) PPEP_PROCESSOR_PARK_STATE Processors;
} PEP_PPM_PARK_MASK, *PPEP_PPM_PARK_MASK;
````

## Members


`Count`

[in] Indicates the number of processors in the <b>Processors</b> array.

`EvaluationTime`

[in] The interrupt time of the performance check evaluation that initiated this notification.

`Processors`

[in/out] An array of processors in the core parking domain. 



#### On input

Indicates the OS parking preference for each processor.



#### On output

Returns the PEP parking preference for each processor.

The Processors array is guaranteed to contain the processors in increasing order by processor index.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186768">PEP_NOTIFY_PPM_PARK_MASK notification</a>



<a href="..\pepfx\ns-pepfx-_pep_processor_park_state.md">PEP_PROCESSOR_PARK_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_PARK_MASK structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>