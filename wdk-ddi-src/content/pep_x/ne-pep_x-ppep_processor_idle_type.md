---
UID : NE:pep_x.PPEP_PROCESSOR_IDLE_TYPE
title : "*PPEP_PROCESSOR_IDLE_TYPE"
author : windows-driver-content
description : The PEP_PROCESSOR_IDLE_TYPE enumeration indicates whether idle constraints apply to just the current processor or to all processors in the hardware platform.
old-location : kernel\pep_processor_idle_type.htm
old-project : kernel
ms.assetid : ABC856E4-557D-45FD-B3A9-3FAA60542343
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PepIdleTypeProcessor, PepIdleTypePlatform, pep_x/PepIdleTypeMax, kernel.pep_processor_idle_type, PEP_PROCESSOR_IDLE_TYPE enumeration [Kernel-Mode Driver Architecture], pep_x/PepIdleTypeProcessor, PepIdleTypeMax, pep_x/PEP_PROCESSOR_IDLE_TYPE, pep_x/PepIdleTypePlatform, *PPEP_PROCESSOR_IDLE_TYPE, PEP_PROCESSOR_IDLE_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : pep_x.h
req.include-header : Pepfx.h
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 10.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPEP_PROCESSOR_IDLE_TYPE, PEP_PROCESSOR_IDLE_TYPE"
---

# *PPEP_PROCESSOR_IDLE_TYPE Enumeration
The <b>PEP_PROCESSOR_IDLE_TYPE</b> enumeration indicates whether idle constraints apply to just the current processor or to all processors in the hardware platform.

## Syntax
````
typedef enum _PEP_PROCESSOR_IDLE_TYPE { 
  PepIdleTypeProcessor  = 0,
  PepIdleTypePlatform,
  PepIdleTypeMax
} PEP_PROCESSOR_IDLE_TYPE;
````

## Constants

<table>

<tr>
<td>PepIdleTypeMax</td>
<td>Reserved for use by operating system.</td>
</tr>

<tr>
<td>PepIdleTypePlatform</td>
<td>Apply to all processors.</td>
</tr>

<tr>
<td>PepIdleTypeProcessor</td>
<td>Apply to current processor.</td>
</tr>
</table>

## Remarks

The <b>Type</b> member of the <a href="..\pep_x\ns-pep_x-_pep_processor_idle_constraints.md">PEP_PROCESSOR_IDLE_CONSTRAINTS</a> structure is a <b>PEP_PROCESSOR_IDLE_TYPE</b> enumeration value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pep_x.h (include Pepfx.h) |

## See Also

<a href="..\pep_x\ns-pep_x-_pep_processor_idle_constraints.md">PEP_PROCESSOR_IDLE_CONSTRAINTS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PROCESSOR_IDLE_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>