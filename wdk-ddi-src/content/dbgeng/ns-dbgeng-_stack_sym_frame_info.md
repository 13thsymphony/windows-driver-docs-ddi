---
UID: NS:dbgeng._STACK_SYM_FRAME_INFO
title: "_STACK_SYM_FRAME_INFO"
author: windows-driver-content
description: Defines stack source information for an extended stack frame.
old-location: debugger\stack_sym_frame_info.htm
old-project: debugger
ms.assetid: 1DE23CF6-970E-4BDE-9BEC-CAC0640B257A
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: PSTACK_SYM_FRAME_INFO, STACK_SYM_FRAME_INFO, debugger.stack_sym_frame_info, *PSTACK_SYM_FRAME_INFO, _STACK_SYM_FRAME_INFO, dbgeng/STACK_SYM_FRAME_INFO, PSTACK_SYM_FRAME_INFO structure pointer [Windows Debugging], STACK_SYM_FRAME_INFO structure [Windows Debugging], dbgeng/PSTACK_SYM_FRAME_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dbgeng.h
apiname:
-	STACK_SYM_FRAME_INFO
product: Windows
targetos: Windows
req.typenames: STACK_SYM_FRAME_INFO, *PSTACK_SYM_FRAME_INFO
---

# _STACK_SYM_FRAME_INFO structure
Defines stack source information for an extended stack frame.

## Syntax
````
typedef struct _STACK_SYM_FRAME_INFO {
  DEBUG_STACK_FRAME_EX StackFrameEx;
  STACK_SRC_INFO       SrcInfo;
} STACK_SYM_FRAME_INFO, *PSTACK_SYM_FRAME_INFO;
````

## Members


`SrcInfo`

Stack source information as a <a href="..\dbgeng\ns-dbgeng-_stack_src_info.md">STACK_SRC_INFO</a> structure.

`StackFrameEx`

A stack frame as a <a href="..\dbgeng\ns-dbgeng-_debug_stack_frame_ex.md">DEBUG_STACK_FRAME_EX</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="..\dbgeng\ns-dbgeng-_debug_stack_frame_ex.md">DEBUG_STACK_FRAME_EX</a>

<a href="..\dbgeng\ns-dbgeng-_stack_src_info.md">STACK_SRC_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20STACK_SYM_FRAME_INFO structure%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>