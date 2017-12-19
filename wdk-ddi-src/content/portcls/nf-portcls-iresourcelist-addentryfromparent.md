---
UID: NF.portcls.IResourceList.AddEntryFromParent
title: IResourceList::AddEntryFromParent method
author: windows-driver-content
description: The AddEntryFromParent method adds to a resource list an entry found in the resource list's parent list.
old-location: audio\iresourcelist_addentryfromparent.htm
old-project: audio
ms.assetid: 83733c17-1f1f-4be6-ae14-aa921e481a73
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IResourceList, IResourceList::AddEntryFromParent, AddEntryFromParent
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
req.alt-api: IResourceList.AddEntryFromParent
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

# IResourceList::AddEntryFromParent method



## -description
The <code>AddEntryFromParent</code> method adds to a resource list an entry found in the resource list's parent list.



## -syntax

````
NTSTATUS AddEntryFromParent(
  [in] struct IResourceList *Parent,
  [in] CM_RESOURCE_TYPE     Type,
  [in] ULONG                Index
);
````


## -parameters

### -param Parent [in]

Pointer to parent <b>IResourceList</b> object from which the entry is to be taken.


### -param Type [in]

Identifies the resource type of the entry that is to be added. For a list of valid resource-type values, see the description of the <b>Type</b> member of the <a href="kernel.cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.


### -param Index [in]

Specifies the index in the parent list of the entry to add. If the parent's <a href="audio.iresourcelist_numberofentriesoftype">IResourceList::NumberOfEntriesOfType</a> method returns a value <i>n</i> for the number of entries of type <i>Type</i>, valid indices range from 0 to <i>n</i>-1. If <i>Index</i> is zero, for example, the method adds the first occurrence of an entry of the specified type from the parent list.


## -returns
<code>AddEntryFromParent</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Indicates there are no free entries in the list.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Indicates the entry was not found in the parent list.

 


## -remarks
For each resource type, a macro is defined to call this method. See <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>.

The <i>Parent</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.


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
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IResourceList::AddEntryFromParent method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

