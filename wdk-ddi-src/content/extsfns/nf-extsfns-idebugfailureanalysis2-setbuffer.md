---
UID: NF:extsfns.IDebugFailureAnalysis2.SetBuffer
title: IDebugFailureAnalysis2::SetBuffer method
author: windows-driver-content
description: The SetBuffer method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it overwrites the data block of the FA entry with the bytes in a specified buffer.
old-location: debugger\idebugfailureanalysis2_setbuffer.htm
old-project: debugger
ms.assetid: 366EE066-AD47-4A75-87B4-17279C66C741
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.idebugfailureanalysis2_setbuffer, SetBuffer method [Windows Debugging], IDebugFailureAnalysis2 interface, SetBuffer, IDebugFailureAnalysis2::SetBuffer, IDebugFailureAnalysis2 interface [Windows Debugging], SetBuffer method, SetBuffer method [Windows Debugging], IDebugFailureAnalysis2, extsfns/IDebugFailureAnalysis2::SetBuffer
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
req.lib: extsfns.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	extsfns.h
apiname:
-	IDebugFailureAnalysis2.SetBuffer
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---


# SetBuffer method
The <b>SetBuffer</b> method searches a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it overwrites the data block of the FA entry with the bytes in a specified buffer. If this method does not find an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has the specified tag, it creates a new FA entry with that tag and overwrites the data block of the new FA entry with the data in the specified buffer.

## Syntax

````
FA_ENTRY SetBuffer(
       FA_TAG        Tag,
  [in] FA_ENTRY_TYPE EntryType,
  [in] PVOID         Buf,
  [in] ULONG         Size
);
````

## Parameters

`Tag`

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

`EntryType`

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_ENTRY_TYPE</a> enumeration. This parameter specifies the data type of the data in <i>Buf</i>.

`Buf`

A pointer to a buffer that contains the bytes to be written to the data block of the new or existing <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>.

`Size`

The size, in bytes, of the buffer pointed to by <i>Buf</i>.


## Return Value

If this method succeeds, it returns a pointer to the new or existing <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.

## Remarks

If this method finds an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, it checks to see whether the data type associated with that tag is compatible with the data type specified by <i>EntryType</i>. For example, <b>DEBUG_FA_ENTRY_ULONG64</b>, <b>DEBUG_FA_ENTRY_INSTRUCTION_OFFSET</b>, and <b>DEBUG_FA_ENTRY_POINTER</b> are all compatible with each other. Likewise, <b>DEBUG_FA_ENTRY_ANSI_STRING</b> and <b>DEBUG_FA_ENTRY_EXTENSION_CMD</b> are compatible with each other. If the data types are not compatible, this method returns <b>NULL</b> and does not overwrite the entry's data block.

If this method does not find an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, it creates a new FA entry with that tag, and it associates the tag with the data type specified by <i>EntryType</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | extsfns.h |
| **Library** | extsfns.h |

## See Also

<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983406">AddBuffer</a>



<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983413">GetBuffer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::SetBuffer method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>