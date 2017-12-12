---
UID: NS.DBGENG._DEBUG_PROCESSOR_IDENTIFICATION_ARM
title: _DEBUG_PROCESSOR_IDENTIFICATION_ARM
author: windows-driver-content
description: Identifies an ARM processor.
old-location: debugger\debug_processor_identification_arm.htm
old-project: debugger
ms.assetid: 4C7D5959-7900-4482-A45C-61D66541C276
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DEBUG_PROCESSOR_IDENTIFICATION_ARM, DEBUG_PROCESSOR_IDENTIFICATION_ARM, *PDEBUG_PROCESSOR_IDENTIFICATION_ARM
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
req.alt-api: DEBUG_PROCESSOR_IDENTIFICATION_ARM
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
---

# _DEBUG_PROCESSOR_IDENTIFICATION_ARM structure



## -description
Identifies an ARM processor. 



## -syntax

````
typedef struct _DEBUG_PROCESSOR_IDENTIFICATION_ARM {
  ULONG Model;
  ULONG Revision;
  CHAR  VendorString[16];
} DEBUG_PROCESSOR_IDENTIFICATION_ARM, *PDEBUG_PROCESSOR_IDENTIFICATION_ARM;
````


## -struct-fields

### -field Model

The model of the processor.


### -field Revision

The revision of the processor.


### -field VendorString

A vendor specified string.


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
<a href="debugger.debug_processor_identification_all">DEBUG_PROCESSOR_IDENTIFICATION_ALL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_PROCESSOR_IDENTIFICATION_ARM structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

