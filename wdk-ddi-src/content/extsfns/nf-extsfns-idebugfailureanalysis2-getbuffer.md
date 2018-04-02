---
UID: NF:extsfns.IDebugFailureAnalysis2.GetBuffer
title: IDebugFailureAnalysis2::GetBuffer method
author: windows-driver-content
description: The GetBuffer method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it gets the entry's data block.
old-location: debugger\idebugfailureanalysis2_getbuffer.htm
old-project: debugger
ms.assetid: 262B5237-86BF-43D6-A29A-A868663EA5D9
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetBuffer method [Windows Debugging], GetBuffer method [Windows Debugging], IDebugFailureAnalysis2 interface, GetBuffer,IDebugFailureAnalysis2.GetBuffer, IDebugFailureAnalysis2, IDebugFailureAnalysis2 interface [Windows Debugging], GetBuffer method, IDebugFailureAnalysis2::GetBuffer, debugger.idebugfailureanalysis2_getbuffer, extsfns/IDebugFailureAnalysis2::GetBuffer
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
-	IDebugFailureAnalysis2.GetBuffer
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---


# IDebugFailureAnalysis2::GetBuffer method
The <b>GetBuffer</b> method searches a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the entry's data block.

## Syntax

```
PFA_ENTRY GetBuffer(
  FA_TAG Tag,
  PVOID  Buf,
  ULONG  Size
);
```

## Parameters

`Tag`

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

`Buf`

A pointer to a buffer that receives the entry's data block.

`Size`

The size, in bytes, of the buffer pointed to by <i>Buf</i>.


## Return Value

If this method finds an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, and if it succeeds in getting the data block, it returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.

## Remarks

If this method finds an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, it checks to see whether the <b>DataSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure is equal to the value specified by the <i>Size</i> parameter. If <b>DataSize</b> is not equal to <i>Size</i>, this method returns <b>NULL</b> and does not get the data block.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | extsfns.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj983406">AddBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983423">SetBuffer</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>