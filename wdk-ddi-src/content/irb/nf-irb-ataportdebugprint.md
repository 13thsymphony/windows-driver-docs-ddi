---
UID: NF.irb.AtaPortDebugPrint
title: AtaPortDebugPrint function
author: windows-driver-content
description: The AtaPortDebugPrint routine passes a message string to the kernel debugger for the debugger to print.
old-location: storage\ataportdebugprint.htm
old-project: storage
ms.assetid: 2a93d30f-4aa0-46b9-b9c7-cc15c62f3053
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: AtaPortDebugPrint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: irb.h
req.include-header: Ata.h, Irb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AtaPortDebugPrint
req.alt-loc: ataport.lib,ataport.dll,pciidex.lib,pciidex.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ataport.lib; Pciidex.lib
req.dll: 
req.irql: 
---

# AtaPortDebugPrint function



## -description
The <b>AtaPortDebugPrint</b> routine passes a message string to the kernel debugger for the debugger to print. 


## -syntax

````
VOID AtaPortDebugPrint(
   ULONG  DebugPrintLevel,
   PCCHAR DebugMessage
);
````


## -parameters

### -param DebugPrintLevel 

Determines how much debug information to display. 

### -param DebugMessage 

A pointer to the debug message to display.

## -returns
None 

## -remarks
The verbosity of debug output is determined by <i>DebugPrintLevel</i> and a port driver-specific mask. Use the <b>nt!kd_idep_mask</b> command to set the desired level of verbosity. For more information about the kernel debugger, see the <a href="https://msdn.microsoft.com/e2490442-9d90-454b-95e0-db8c5d7fa19a">Using a Debugger</a> topic 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Irb.h (include Ata.h or Irb.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ataport.lib; </dt>
<dt>Pciidex.lib</dt>
</dl>
</td>
</tr>
</table>