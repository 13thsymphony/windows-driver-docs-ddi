---
UID: NF.portcls.IResourceList.NumberOfEntriesOfType
title: IResourceList::NumberOfEntriesOfType method
author: windows-driver-content
description: The NumberOfEntriesOfType method returns the number of resource items of a given type in the resource list. For each resource type, a macro is defined to call this method as previously described.
old-location: audio\iresourcelist_numberofentriesoftype.htm
old-project: audio
ms.assetid: 61645c17-9278-49e0-a0bf-24a8c52e964d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IResourceList, IResourceList::NumberOfEntriesOfType, NumberOfEntriesOfType
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
req.alt-api: IResourceList.NumberOfEntriesOfType
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

# IResourceList::NumberOfEntriesOfType method



## -description
The <code>NumberOfEntriesOfType</code> method returns the number of resource items of a given type in the resource list. For each resource type, a macro is defined to call this method as previously described.



## -syntax

````
ULONG NumberOfEntriesOfType(
  [in] CM_RESOURCE_TYPE Type
);
````


## -parameters

### -param Type [in]

Identifies the resource type of the entries that are to be counted. For a list of valid resource-type values, see the <b>Type</b> member of the <a href="kernel.cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.


## -returns
<code>NumberOfEntriesOfType</code> returns the number of items of the indicated type in the resource list.


## -remarks
For each resource type, a macro is defined to call this method. See <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>.


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
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IResourceList::NumberOfEntriesOfType method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

