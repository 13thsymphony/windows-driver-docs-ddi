---
UID: NC:wdbgexts.PWINDBG_DISASM
title: PWINDBG_DISASM
author: windows-driver-content
description: The PWINDBG_DISASM (Disasm) function disassembles the instruction pointed to by lpOffset and places the printable string into lpBuffer.
old-location: debugger\disasm.htm
old-project: debugger
ms.assetid: 1a986b7b-b45b-4546-a14e-4abb76ddf764
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Disasm, Disasm callback function [Windows Debugging], PWINDBG_DISASM, WdbgExts_Ref_787ab353-1829-4111-8931-2192bfb9cd0c.xml, debugger.disasm, wdbgexts/Disasm
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdbgexts.h
api_name:
-	Disasm
product: Windows
targetos: Windows
req.typenames: VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
req.product: Windows 10 or later.
---


# PWINDBG_DISASM callback function
The <b>PWINDBG_DISASM</b> (<b>Disasm</b>) function disassembles the instruction pointed to by <i>lpOffset</i> and places the printable string into <i>lpBuffer</i>.

## Syntax

```
PWINDBG_DISASM PwindbgDisasm;

ULONG PwindbgDisasm(
  ULONG_PTR *lpOffset,
  PCSTR lpBuffer,
  ULONG fShowEffectiveAddress
)
{...}
```

## Parameters

`*lpOffset`

Points to the instruction to be disassembled.

`lpBuffer`

Receives the disassembled instruction.

`fShowEffectiveAddress`

Specifies whether or not to print the effective address.


## Return Value

If the routine succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |