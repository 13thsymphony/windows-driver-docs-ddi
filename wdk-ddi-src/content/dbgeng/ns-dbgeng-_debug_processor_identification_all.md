---
UID: NS:dbgeng._DEBUG_PROCESSOR_IDENTIFICATION_ALL
title: _DEBUG_PROCESSOR_IDENTIFICATION_ALL
author: windows-driver-content
description: This union contains relevant information for a processor the supported processors.
old-location: debugger\debug_processor_identification_all.htm
old-project: debugger
ms.assetid: 2C4C03BC-0D84-4151-B1A1-FE76F0355CD6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DEBUG_PROCESSOR_IDENTIFICATION_ALL, *PDEBUG_PROCESSOR_IDENTIFICATION_ALL, DEBUG_PROCESSOR_IDENTIFICATION_ALL
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
req.alt-api: DEBUG_PROCESSOR_IDENTIFICATION_ALL
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
req.typenames: *PDEBUG_PROCESSOR_IDENTIFICATION_ALL, DEBUG_PROCESSOR_IDENTIFICATION_ALL
---

# _DEBUG_PROCESSOR_IDENTIFICATION_ALL structure



## -description
This union contains relevant information for a processor the supported processors. 



## -syntax

````
typedef union _DEBUG_PROCESSOR_IDENTIFICATION_ALL {
  DEBUG_PROCESSOR_IDENTIFICATION_ALPHA Alpha;
  DEBUG_PROCESSOR_IDENTIFICATION_AMD64 Amd64;
  DEBUG_PROCESSOR_IDENTIFICATION_IA64  Ia64;
  DEBUG_PROCESSOR_IDENTIFICATION_X86   X86;
  DEBUG_PROCESSOR_IDENTIFICATION_ARM   Arm;
  DEBUG_PROCESSOR_IDENTIFICATION_ARM64 Arm64;
} DEBUG_PROCESSOR_IDENTIFICATION_ALL;
````


## -struct-fields

### -field Alpha

An Alpha processor as a <a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_alpha.md">DEBUG_PROCESSOR_IDENTIFICATION_ALPHA</a> struct.


### -field Amd64

An AMD64 processor as a <a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_amd64.md">DEBUG_PROCESSOR_IDENTIFICATION_AMD64</a> stuct. 


### -field Ia64

An Italium architecture processor as a <a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_ia64.md">DEBUG_PROCESSOR_IDENTIFICATION_IA64</a> stuct.


### -field X86

An x86 processor as a <a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_x86.md">DEBUG_PROCESSOR_IDENTIFICATION_X86</a> struct.


### -field Arm

An ARM processor as a <a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_arm.md">DEBUG_PROCESSOR_IDENTIFICATION_ARM</a> struct.


### -field Arm64

An ARM64 processor as a <a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_arm64.md">DEBUG_PROCESSOR_IDENTIFICATION_ARM64</a> struct. 


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
<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_alpha.md">DEBUG_PROCESSOR_IDENTIFICATION_ALPHA</a>
</dt>
<dt>
<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_amd64.md">DEBUG_PROCESSOR_IDENTIFICATION_AMD64</a>
</dt>
<dt>
<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_arm.md">DEBUG_PROCESSOR_IDENTIFICATION_ARM</a>
</dt>
<dt>
<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_arm64.md">DEBUG_PROCESSOR_IDENTIFICATION_ARM64</a>
</dt>
<dt>
<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_ia64.md">DEBUG_PROCESSOR_IDENTIFICATION_IA64</a>
</dt>
<dt>
<a href="..\dbgeng\ns-dbgeng-_debug_processor_identification_x86.md">DEBUG_PROCESSOR_IDENTIFICATION_X86</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_PROCESSOR_IDENTIFICATION_ALL union%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

