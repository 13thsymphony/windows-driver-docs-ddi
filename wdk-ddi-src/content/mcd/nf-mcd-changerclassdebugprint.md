---
UID: NF:mcd.ChangerClassDebugPrint
title: ChangerClassDebugPrint function
author: windows-driver-content
description: The ChangerClassDebugPrint function prints debugging information.
old-location: storage\changerclassdebugprint.htm
old-project: storage
ms.assetid: 452377f1-a926-4f43-8168-bea11622902e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ChangerClassDebugPrint, storage.changerclassdebugprint, ChangerClassDebugPrint function [Storage Devices], mcd/ChangerClassDebugPrint, chgrclas_3372885c-482b-4dab-87ae-e59668e91950.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
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
req.lib: Mcd.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Mcd.lib
-	Mcd.dll
apiname:
-	ChangerClassDebugPrint
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---


# ChangerClassDebugPrint function
The <b>ChangerClassDebugPrint</b> function prints debugging information.

## Syntax

````
VOID ChangerClassDebugPrint(
   ULONG  DebugPrintLevel,
   PCCHAR DebugMessage
);
````

## Parameters

`DebugPrintLevel`

Indicates how verbose debug information should be. Caller must assign this parameter an integer value between zero and three, where three specifies the highest level of verbosity and zero the lowest.

`DebugMessage`

Caller can specify a message to be included with the debugging information that is printed by assigning a printable ASCII character string to this parameter.

`Arg1`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | mcd.h (include Mcd.h, Ntddchgr.h) |
| **Library** | Mcd.lib |