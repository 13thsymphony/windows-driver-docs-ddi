---
UID: NF.extsfns.IDebugFAEntryTags.GetProperties
title: IDebugFAEntryTags::GetProperties method
author: windows-driver-content
description: The GetProperties method gets the name or description (or both) of a tag in a DebugFailureAnalysisTags object.
old-location: debugger\idebugfaentrytags_getproperties.htm
old-project: Debugger
ms.assetid: 140EAE7D-E349-4096-8578-6CF011C1FBA7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugFAEntryTags, IDebugFAEntryTags::GetProperties, GetProperties
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
req.alt-api: IDebugFAEntryTags.GetProperties
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
---

# IDebugFAEntryTags::GetProperties method



## -description
The <b>GetProperties</b> method gets the name or description (or both) of a tag in a <a href="debugger.idebugfaentrytags">DebugFailureAnalysisTags</a> object.



## -syntax

````
HRESULT GetProperties(
            FA_TAG  Tag,
  [out]     PSTR    Name,
  [in, out] PULONG  NameSize,
  [out]     PSTR    Description,
  [in, out] PULONG  DescSize,
  [out]     PULONG  Flags
);
````


## -parameters

### -param Tag 

A value in the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991810">FA_TAG</a> enumeration. This method gets the name or description (or both) of this tag.


### -param Name [out]

A pointer to a buffer that receives a null-terminated string that is the name of the tag. If <i>NameSize</i> is less than the length of the tag's name, this method copies only <i>NameSize</i> bytes, including the <b>NULL</b> terminator, to this buffer.


### -param NameSize [in, out]

On input, this parameter, specifies the size, in bytes, of the buffer pointed to by <i>Name</i>. On output, this parameter receives the size, in bytes, of the name of the tag. If the tag has no name, this parameter receives a value of 0.

<div class="alert"><b>Note</b>  If <i>Name</i> is NULL, this parameter receives no information. You should either set both <i>Name</i> and <i>NameSize</i> to non-NULL values or set them both to <b>NULL</b>.</div>
<div> </div>

### -param Description [out]

A pointer to a buffer that receives a null-terminated string that is the description of the tag. If <i>DescSize</i> is less than the length of the tag's description, this method copies only <i>DescSize</i> bytes, including the <b>NULL</b> terminator, to this buffer.


### -param DescSize [in, out]

On input, this parameter, specifies the size, in bytes, of the buffer pointed to by <i>Description</i>. On output, this parameter receives the size, in bytes, of the description of the tag. If the tag has no description, this parameter receives a value of 0.

<div class="alert"><b>Note</b>  If <i>Description</i> is NULL, this parameter receives no information. You should either set both <i>Description</i> and <i>DescSize</i> to non-NULL values or set them both to <b>NULL</b>.</div>
<div> </div>

### -param Flags [out]

Reserved. Set this parameter to NULL.


## -returns
The <b>HRESULT</b> values returned by this method are defined in winerror.h and strsafe.h. The values returned by this method include, but are not limited to the following:
<dl>
<dt><b>S_OK</b></dt>
</dl>This method successfully retrieved the requested name or description  (or both), and no truncation of the requested string or strings was required.
<dl>
<dt><b>STRSAFE_E_INSUFFICIENT_BUFFER</b></dt>
</dl>This method retrieved the requested name or description (or both), but the name or description was truncated.
<dl>
<dt><b>STRSAFE_E_INVALID_PARAMETER </b></dt>
</dl>The caller passed at least one invalid parameter.

 


## -remarks


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
<dt>Extsfns.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="debugger.idebugfaentrytags">IDebugFAEntryTags</a>
</dt>
<dt>
<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>
</dt>
<dt>
<a href="debugger.idebugfaentrytags_setproperties">SetProperties</a>
</dt>
<dt>
<a href="debugger._efn_analyze">_EFN_Analyze</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugFAEntryTags::GetProperties method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

