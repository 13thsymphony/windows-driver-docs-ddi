---
UID: NF:wdbgexts.WritePointer
title: WritePointer function
author: windows-driver-content
description: The WritePointer function writes a pointer to the target.
old-location: debugger\writepointer.htm
old-project: debugger
ms.assetid: 5f3d6cd6-e138-4114-8fac-03cbe1c7aa68
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdbgExts_Ref_ab18dbae-3a69-43a1-97dd-d0711e4db54e.xml, WritePointer, WritePointer function [Windows Debugging], debugger.writepointer, wdbgexts/WritePointer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	WritePointer
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---


# WritePointer function
The <b>WritePointer</b> function writes a pointer to the target.

## Syntax

````
ULONG WritePointer(
   ULONG64 Address,
   ULONG64 Pointer
);
````

## Parameters

`Address`

Specifies the address to write the pointer to.

`Pointer`

Specifies the value of the pointer.  If the target uses 32-bit pointers, <i>Pointer</i> is a 32-bit value that has been sign-extended to 64-bits.


## Return Value

If the function succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.

## Remarks

For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\wdbgexts\nf-wdbgexts-readpointer.md">ReadPointer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20WritePointer function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>