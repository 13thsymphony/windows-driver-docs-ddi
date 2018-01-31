---
UID : NF:extsfns.IDebugFAEntryTags.SetType
title : IDebugFAEntryTags::SetType method
author : windows-driver-content
description : The SetType method sets the data type that is associated with a tag in a DebugFailureAnalysisTags object.
old-location : debugger\idebugfaentrytags_settype.htm
old-project : debugger
ms.assetid : F507864B-B20C-4F71-B068-802780243106
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : debugger.idebugfaentrytags_settype, IDebugFAEntryTags::SetType, IDebugFAEntryTags interface [Windows Debugging], SetType method, SetType method [Windows Debugging], SetType, SetType method [Windows Debugging], IDebugFAEntryTags interface, IDebugFAEntryTags, extsfns/IDebugFAEntryTags::SetType
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


# SetType method
The <b>SetType</b> method sets the data type that is associated with a tag in a <a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">DebugFailureAnalysisTags</a> object.

## Syntax

````
HRESULT SetType(
  [in] FA_TAG        Tag,
  [in] FA_ENTRY_TYPE EntryType
);
````

## Parameters

`Tag`

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

`EntryType`

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_ENTRY_TYPE</a> enumeration.


## Return Value

If this method successfully sets the data type of <i>Tag</i> to <i>EntryType</i>, it returns <b>S_OK</b>. Otherwise, it returns <b>E_INVALIDARG</b>.

## Remarks

This method checks to see whether the data type for <i>Tag</i> has already been set. If the data type has not already been set, this method sets the data type to <i>EntryType</i>.

If the data type for <i>Tag</i> has already been set, this method checks to see whether <i>EntryType</i> is compatible with the data type that has already been set. If the data types are compatible, this method sets (overwrites) the data type for <i>Tag</i> to <i>EntryType</i>. If the data types are not compatible, this method returns <b>E_INVALIDARG</b> and does not set the data type.

The data types <b>DEBUG_FA_ENTRY_ULONG64</b>, <b>DEBUG_FA_ENTRY_INSTRUCTION_OFFSET</b>, and <b>DEBUG_FA_ENTRY_POINTER</b> are compatible.

The data types <b>DEBUG_FA_ENTRY_ANSI_STRING</b> and <b>DEBUG_FA_ENTRY_EXTENSION_CMD</b> are compatible.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | extsfns.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTags</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/jj991813">GetType</a>

<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>

<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>

<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFAEntryTags::SetType method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>