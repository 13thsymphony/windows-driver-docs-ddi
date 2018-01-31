---
UID : NS:dbgeng._DEBUG_OFFSET_REGION
title : "_DEBUG_OFFSET_REGION"
author : windows-driver-content
description : Defines a debug offset region.
old-location : debugger\debug_offset_region.htm
old-project : debugger
ms.assetid : 7116B31A-D584-4B9D-AFB4-5B15B659BE54
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : PDEBUG_OFFSET_REGION, debugger.debug_offset_region, dbgeng/PDEBUG_OFFSET_REGION, DEBUG_OFFSET_REGION structure [Windows Debugging], *PDEBUG_OFFSET_REGION, DEBUG_OFFSET_REGION, _DEBUG_OFFSET_REGION, dbgeng/DEBUG_OFFSET_REGION, PDEBUG_OFFSET_REGION structure pointer [Windows Debugging]
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DEBUG_OFFSET_REGION, *PDEBUG_OFFSET_REGION
---

# _DEBUG_OFFSET_REGION structure
Defines a debug offset region.

## Syntax
````
typedef struct _DEBUG_OFFSET_REGION {
  ULONG64 Base;
  ULONG64 Size;
} DEBUG_OFFSET_REGION, *PDEBUG_OFFSET_REGION;
````

## Members


`Base`

The base value of the offset region.

`Size`

The size of the region.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include DbgEng.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugadvanced.md">IDebugAdvanced</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_OFFSET_REGION structure%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>