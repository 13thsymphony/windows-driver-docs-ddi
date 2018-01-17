---
UID: NF:extsfns.IDebugFAEntryTags.GetType
title: IDebugFAEntryTags::GetType method
author: windows-driver-content
description: The GetType method gets the data type that is associated with a tag in a DebugFailureAnalysisTags object.
old-location: debugger\idebugfaentrytags_gettype.htm
old-project: debugger
ms.assetid: CE43711F-E17B-4234-A885-4FE04EA53903
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugFAEntryTags, IDebugFAEntryTags::GetType, GetType
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
req.alt-api: IDebugFAEntryTags.GetType
req.alt-loc: extsfns.h
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
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFAEntryTags::GetType method



## -description
The <b>GetType</b> method gets the data type that is associated with a tag in a <a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">DebugFailureAnalysisTags</a> object.



## -syntax

````
FA_ENTRY_TYPE GetType(
   FA_TAG Tag
);
````


## -parameters

### -param Tag 

A value in the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991810">FA_TAG</a> enumeration.


## -returns
A value in the <a href="..\extsfns\ne-extsfns-_fa_entry_type.md">FA_ENTRY_TYPE</a> enumeration.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTags</a>
</dt>
<dt>
<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj991816">SetType</a>
</dt>
<dt>
<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFAEntryTags::GetType method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

