---
UID : NS:dbgeng._DEBUG_PROCESSOR_IDENTIFICATION_IA64
title : _DEBUG_PROCESSOR_IDENTIFICATION_IA64
author : windows-driver-content
description : Identifies an Intel Itanium architecture (IA64) processor.
old-location : debugger\debug_processor_identification_ia64.htm
old-project : debugger
ms.assetid : 8827D989-EB59-4474-97D8-9CD9BF24FCC1
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _DEBUG_PROCESSOR_IDENTIFICATION_IA64, DEBUG_PROCESSOR_IDENTIFICATION_IA64, *PDEBUG_PROCESSOR_IDENTIFICATION_IA64
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dbgeng.h
req.include-header : DbgEng.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DEBUG_PROCESSOR_IDENTIFICATION_IA64
req.alt-loc : DbgEng.h
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
req.typenames : DEBUG_PROCESSOR_IDENTIFICATION_IA64, *PDEBUG_PROCESSOR_IDENTIFICATION_IA64
---

# _DEBUG_PROCESSOR_IDENTIFICATION_IA64 structure
Identifies an Intel Itanium  architecture (IA64) processor.

## Syntax
````
typedef struct _DEBUG_PROCESSOR_IDENTIFICATION_IA64 {
  ULONG Model;
  ULONG Revision;
  ULONG Family;
  ULONG ArchRev;
  CHAR  VendorString[16];
} DEBUG_PROCESSOR_IDENTIFICATION_IA64, *PDEBUG_PROCESSOR_IDENTIFICATION_IA64;
````

## Members

        
            `ArchRev`

            The architecture revision of the processor.
        
            `Family`

            The family of the processor.
        
            `Model`

            The model of the processor.
        
            `Revision`

            The revision of the processor.
        
            `VendorString`

            A vendor specified string.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include DbgEng.h) |

    ## See Also

        <dl>
<dt>
<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_all.md">DEBUG_PROCESSOR_IDENTIFICATION_ALL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_PROCESSOR_IDENTIFICATION_IA64 structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>