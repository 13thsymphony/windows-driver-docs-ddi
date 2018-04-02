---
UID: NF:extsfns.IDebugFailureAnalysis2.NextEntry
title: IDebugFailureAnalysis2::NextEntry method
author: windows-driver-content
description: The NextEntry method gets the next FA entry, after a given FA entry, in a DebugFailureAnalysis object.
old-location: debugger\idebugfailureanalysis2_nextentry.htm
old-project: debugger
ms.assetid: B5640B86-D931-4A26-85F2-BBE18620668C
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugFailureAnalysis2, IDebugFailureAnalysis2 interface [Windows Debugging], NextEntry method, IDebugFailureAnalysis2::NextEntry, NextEntry method [Windows Debugging], NextEntry method [Windows Debugging], IDebugFailureAnalysis2 interface, NextEntry,IDebugFailureAnalysis2.NextEntry, debugger.idebugfailureanalysis2_nextentry, extsfns/IDebugFailureAnalysis2::NextEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: extsfns.h
req.include-header: 
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
-	COM
api_location:
-	extsfns.h
api_name:
-	IDebugFailureAnalysis2.NextEntry
product:
- Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---


# IDebugFailureAnalysis2::NextEntry method
The <b>NextEntry</b> method gets the next <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>, after a given FA entry, in a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object.

## Syntax

```
PFA_ENTRY NextEntry(
  PFA_ENTRY Entry
);
```

## Parameters

`Entry`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure. This method returns the next entry after this entry. If this parameter is <b>NULL</b>, this method returns the first <b>FA_ENTRY</b> in the <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object.


## Return Value

This method returns a pointer to the next (or first) <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure. If there are no more <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entries</a> in the <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object, this method returns <i>NULL</i>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | extsfns.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj983411">Get</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983418">GetNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>