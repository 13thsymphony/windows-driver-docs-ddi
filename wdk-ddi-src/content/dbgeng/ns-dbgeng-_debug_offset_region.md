---
UID: NS:dbgeng._DEBUG_OFFSET_REGION
title: _DEBUG_OFFSET_REGION
author: windows-driver-content
description: Defines a debug offset region.
old-location: debugger\debug_offset_region.htm
old-project: debugger
ms.assetid: 7116B31A-D584-4B9D-AFB4-5B15B659BE54
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DEBUG_OFFSET_REGION, DEBUG_OFFSET_REGION, *PDEBUG_OFFSET_REGION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEBUG_OFFSET_REGION
req.alt-loc: DbgEng.h
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
req.typenames: DEBUG_OFFSET_REGION, *PDEBUG_OFFSET_REGION
---

# _DEBUG_OFFSET_REGION structure



## -description
Defines a debug offset region.



## -syntax

````
typedef struct _DEBUG_OFFSET_REGION {
  ULONG64 Base;
  ULONG64 Size;
} DEBUG_OFFSET_REGION, *PDEBUG_OFFSET_REGION;
````


## -struct-fields

### -field Base

The base value of the offset region.


### -field Size

The size of the region. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>DbgEng.h (include DbgEng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugadvanced.md">IDebugAdvanced</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_OFFSET_REGION structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

