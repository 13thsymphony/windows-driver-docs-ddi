---
UID: NF.portcls.IResourceList.FindUntranslatedEntry
title: IResourceList::FindUntranslatedEntry method
author: windows-driver-content
description: The FindUntranslatedEntry method returns a pointer to an untranslated entry of the specified type, or NULL if no such pointer is found.
old-location: audio\iresourcelist_finduntranslatedentry.htm
old-project: audio
ms.assetid: 3578eb3a-e9c8-4de3-b959-daff9ac7f1a2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IResourceList, IResourceList::FindUntranslatedEntry, FindUntranslatedEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IResourceList.FindUntranslatedEntry
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# IResourceList::FindUntranslatedEntry method



## -description
The <code>FindUntranslatedEntry</code> method returns a pointer to an untranslated entry of the specified type, or <b>NULL</b> if no such pointer is found.



## -syntax

````
PCM_PARTIAL_RESOURCE_DESCRIPTOR FindUntranslatedEntry(
  [in] CM_RESOURCE_TYPE Type,
  [in] ULONG            Index
);
````


## -parameters

### -param Type [in]

Identifies the resource type of the entries that are to be counted. For a list of valid values, see the <b>Type</b> member of the <a href="kernel.cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.


### -param Index [in]

Specifies the index of the entry to find. If the <a href="audio.iresourcelist_numberofentriesoftype">IResourceList::NumberOfEntriesOfType</a> method returns a value <i>n</i> for the number of entries of type <i>Type</i>, valid indices range from 0 to <i>n</i>-1. If <i>Index</i> is zero, for example, the method returns a pointer to the untranslated version of the first occurrence of an entry of the specified type from the resource list.


## -returns
<code>FindUntranslatedEntry</code> returns a pointer to the specified entry or is <b>NULL</b> if the entry does not exist. This pointer remains valid until the resource object is deleted.


## -remarks
For each resource type, a macro is defined to call this method. See <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>.

The <i>Index</i> parameter indicates which occurrence of an entry of the specified type to find in the list of translated resource entries. The first occurrence in the list has an index of zero.

For more information about translated and untranslated (or "raw") resources, see <a href="kernel.cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>
</dt>
<dt>
<a href="kernel.cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="audio.iresourcelist_numberofentriesoftype">IResourceList::NumberOfEntriesOfType</a>
</dt>
<dt>
<a href="audio.iresourcelist_findtranslatedentry">IResourceList::FindTranslatedEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IResourceList::FindUntranslatedEntry method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

