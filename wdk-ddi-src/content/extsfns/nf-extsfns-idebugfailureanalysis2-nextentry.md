---
UID: NF.extsfns.IDebugFailureAnalysis2.NextEntry
title: IDebugFailureAnalysis2::NextEntry
author: windows-driver-content
description: The NextEntry method gets the next FA entry, after a given FA entry, in a DebugFailureAnalysis object.
old-location: debugger\idebugfailureanalysis2_nextentry.htm
old-project: debugger
ms.assetid: B5640B86-D931-4A26-85F2-BBE18620668C
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugFailureAnalysis2, NextEntry, IDebugFailureAnalysis2::NextEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: extsfns.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugFailureAnalysis2.NextEntry
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
req.iface: IDebugFailureAnalysis2
---

# IDebugFailureAnalysis2::NextEntry method



## -description
<p>The <b>NextEntry</b> method gets the next <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>, after a given FA entry, in a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object.</p>


## -syntax

````
PFA_ENTRY NextEntry(
   PFA_ENTRY  Entry
);
````


## -parameters
<dl>

### -param  Entry 

<dd>
<p>A pointer to an <a href="..\extsfns\ns-extsfns--fa-entry.md">FA_ENTRY</a> structure. This method returns the next entry after this entry. If this parameter is <b>NULL</b>, this method returns the first <b>FA_ENTRY</b> in the <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object.</p>
</dd>
</dl>

## -returns
<p>This method returns a pointer to the next (or first) <a href="..\extsfns\ns-extsfns--fa-entry.md">FA_ENTRY</a> structure. If there are no more <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entries</a> in the <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object, this method returns <i>NULL</i>.</p>

<p>The following example shows how to iterate through all the <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entries</a> in a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object. Assume <i>pAnalysis</i> is a pointer to an <b>IDebugFailureAnalysis2</b> interface.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Extsfns.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>
</dt>
<dt>
<a href="debugger.idebugfailureanalysis2_get">Get</a>
</dt>
<dt>
<a href="debugger.idebugfailureanalysis2_getnext">GetNext</a>
</dt>
<dt>
<a href="debugger._efn_analyze">_EFN_Analyze</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::NextEntry method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
