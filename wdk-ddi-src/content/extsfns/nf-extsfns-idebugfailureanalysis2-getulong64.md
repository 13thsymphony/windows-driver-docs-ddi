---
UID : NF:extsfns.IDebugFailureAnalysis2.GetUlong64
title : IDebugFailureAnalysis2::GetUlong64 method
author : windows-driver-content
description : The GetUlong64 method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it gets the ULONG64 value from the entry's data block.
old-location : debugger\idebugfailureanalysis2_getulong64.htm
old-project : debugger
ms.assetid : C00C983A-92BA-4E4A-A5AB-918121D14B64
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugFailureAnalysis2 interface [Windows Debugging], GetUlong method, IDebugFailureAnalysis2, debugger.idebugfailureanalysis2_getulong64, GetUlong method [Windows Debugging], IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2::GetUlong, GetUlong method [Windows Debugging], GetUlong64, extsfns/IDebugFailureAnalysis2::GetUlong, IDebugFailureAnalysis2::GetUlong64
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : extsfns.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : extsfns.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : FA_EXTENSION_PLUGIN_PHASE
---


# GetUlong64 method
The <b>GetUlong64</b> method searches a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the <b>ULONG64</b> value from the entry's data block.

## Syntax

````
PFA_ENTRY GetUlong(
        FA_TAG   Tag,
  [out] PULONG64 Value
);
````

## Parameters

`Tag`

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

`Value`

A pointer to a <b>ULONG64</b> that receives the value from the entry's data block.


## Return Value

If this method finds an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, and if it succeeds in getting the data block, it returns a pointer to the <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.

## Remarks

If this method finds an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, it checks to see whether the <b>DataSize</b> member of the <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure is equal to the size of a <b>ULONG64</b>. If <b>DataSize</b> is not equal to the size of a <b>ULONG64</b>, this method returns <b>NULL</b> and does not get the data block.

Each tag that has already been used in a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object is associated with one of the data types in the <a href="..\extsfns\ne-extsfns-_fa_entry_type.md">FA_ENTRY_TYPE</a> enumeration. To determine the data type associated with a tag, call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991813">GetType</a> method of the <a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTags</a> interface. To get a pointer to an IDebugFAEntryTags interface, call the <a href="https://msdn.microsoft.com/library/windows/hardware/jj983414">GetDebugFATagControl</a> method of the <b>IDebugFailureAnalysis2</b> interface.

The appropriate use of this method is get the data block from an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a data type of <b>DEBUG_FA_ENTRY_ULONG64</b> or <b>DEBUG_FA_ENTRY_INSTRUCTION_OFFSET</b> or <b>DEBUG_FA_ENTRY_POINTER</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | extsfns.h |
| **Library** | extsfns.h |

## See Also

<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>

<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/jj983426">SetUlong64</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/jj983410">AddUlong64</a>

<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::GetUlong method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>