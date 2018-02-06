---
UID: NF:extsfns.IDebugFAEntryTags.IsValidTagToSet
title: IDebugFAEntryTags::IsValidTagToSet method
author: windows-driver-content
description: The IsValidTagToSet method determines whether it is OK to set the data of a specified tag.
old-location: debugger\idebugfaentrytags_isvalidtagtoset.htm
old-project: debugger
ms.assetid: 83B5C54F-182B-4D2F-8ED2-7A0B529F1D2E
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugFAEntryTags interface [Windows Debugging], IsValidTagToSet method, IsValidTagToSet, IDebugFAEntryTags::IsValidTagToSet, debugger.idebugfaentrytags_isvalidtagtoset, extsfns/IDebugFAEntryTags::IsValidTagToSet, IsValidTagToSet method [Windows Debugging], IsValidTagToSet method [Windows Debugging], IDebugFAEntryTags interface, IDebugFAEntryTags
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
-	IDebugFAEntryTags.IsValidTagToSet
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---


# IsValidTagToSet method
The <b>IsValidTagToSet</b> method determines whether it is OK to set the data of a specified tag.

## Syntax

````
BOOL IsValidTagToSet(
   FA_TAG Tag
);
````

## Parameters

`Tag`

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


## Return Value

This method returns TRUE if it is OK to set the data of the specified tag. Otherwise it returns FALSE.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | extsfns.h |
| **Library** | extsfns.h |

## See Also

<a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTags</a>

<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>

<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>

<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFAEntryTags::IsValidTagToSet method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>