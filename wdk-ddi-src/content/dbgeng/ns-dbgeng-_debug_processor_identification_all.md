---
UID: NS:dbgeng._DEBUG_PROCESSOR_IDENTIFICATION_ALL
title: "_DEBUG_PROCESSOR_IDENTIFICATION_ALL"
author: windows-driver-content
description: This union contains relevant information for a processor the supported processors.
old-location: debugger\debug_processor_identification_all.htm
old-project: debugger
ms.assetid: 2C4C03BC-0D84-4151-B1A1-FE76F0355CD6
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PDEBUG_PROCESSOR_IDENTIFICATION_ALL, DEBUG_PROCESSOR_IDENTIFICATION_ALL, DEBUG_PROCESSOR_IDENTIFICATION_ALL union [Windows Debugging], _DEBUG_PROCESSOR_IDENTIFICATION_ALL, dbgeng/DEBUG_PROCESSOR_IDENTIFICATION_ALL, debugger.debug_processor_identification_all"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	DbgEng.h
api_name:
-	DEBUG_PROCESSOR_IDENTIFICATION_ALL
product: Windows
targetos: Windows
req.typenames: DEBUG_PROCESSOR_IDENTIFICATION_ALL, *PDEBUG_PROCESSOR_IDENTIFICATION_ALL
---

# _DEBUG_PROCESSOR_IDENTIFICATION_ALL structure
This union contains relevant information for a processor the supported processors.

## Syntax
```
typedef struct _DEBUG_PROCESSOR_IDENTIFICATION_ALL {
  DEBUG_PROCESSOR_IDENTIFICATION_ALPHA Alpha;
  DEBUG_PROCESSOR_IDENTIFICATION_AMD64 Amd64;
  DEBUG_PROCESSOR_IDENTIFICATION_IA64  Ia64;
  DEBUG_PROCESSOR_IDENTIFICATION_X86   X86;
  DEBUG_PROCESSOR_IDENTIFICATION_ARM   Arm;
  DEBUG_PROCESSOR_IDENTIFICATION_ARM64 Arm64;
} *PDEBUG_PROCESSOR_IDENTIFICATION_ALL, DEBUG_PROCESSOR_IDENTIFICATION_ALL;
```

## Members


`Alpha`

An Alpha processor as a <a href="https://msdn.microsoft.com/AE0DB2CC-6364-4B50-8CD3-8EF8B495FBED">DEBUG_PROCESSOR_IDENTIFICATION_ALPHA</a> struct.

`Amd64`

An AMD64 processor as a <a href="https://msdn.microsoft.com/71E28D54-19D2-4A62-9A63-633186F67AD5">DEBUG_PROCESSOR_IDENTIFICATION_AMD64</a> stuct.

`Ia64`

An Italium architecture processor as a <a href="https://msdn.microsoft.com/8827D989-EB59-4474-97D8-9CD9BF24FCC1">DEBUG_PROCESSOR_IDENTIFICATION_IA64</a> stuct.

`X86`

An x86 processor as a <a href="https://msdn.microsoft.com/B5AD9CE8-B0F0-49BC-984E-4372FD3BF93B">DEBUG_PROCESSOR_IDENTIFICATION_X86</a> struct.

`Arm`

An ARM processor as a <a href="https://msdn.microsoft.com/4C7D5959-7900-4482-A45C-61D66541C276">DEBUG_PROCESSOR_IDENTIFICATION_ARM</a> struct.

`Arm64`

An ARM64 processor as a <a href="https://msdn.microsoft.com/4F47EC75-4D68-4202-9B29-8F6FB36528A5">DEBUG_PROCESSOR_IDENTIFICATION_ARM64</a> struct.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | dbgeng.h (include DbgEng.h) |

## See Also

<a href="https://msdn.microsoft.com/AE0DB2CC-6364-4B50-8CD3-8EF8B495FBED">DEBUG_PROCESSOR_IDENTIFICATION_ALPHA</a>



<a href="https://msdn.microsoft.com/71E28D54-19D2-4A62-9A63-633186F67AD5">DEBUG_PROCESSOR_IDENTIFICATION_AMD64</a>



<a href="https://msdn.microsoft.com/4C7D5959-7900-4482-A45C-61D66541C276">DEBUG_PROCESSOR_IDENTIFICATION_ARM</a>



<a href="https://msdn.microsoft.com/4F47EC75-4D68-4202-9B29-8F6FB36528A5">DEBUG_PROCESSOR_IDENTIFICATION_ARM64</a>



<a href="https://msdn.microsoft.com/8827D989-EB59-4474-97D8-9CD9BF24FCC1">DEBUG_PROCESSOR_IDENTIFICATION_IA64</a>



<a href="https://msdn.microsoft.com/B5AD9CE8-B0F0-49BC-984E-4372FD3BF93B">DEBUG_PROCESSOR_IDENTIFICATION_X86</a>