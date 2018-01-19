---
UID : NF:portcls.IResourceList.FindTranslatedEntry
title : IResourceList::FindTranslatedEntry method
author : windows-driver-content
description : The FindTranslatedEntry method returns a pointer to a translated entry of the specified type, or NULL if no such entry is found.
old-location : audio\iresourcelist_findtranslatedentry.htm
old-project : audio
ms.assetid : b3e8ae4d-a923-406e-ad1a-f7ed7277f676
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : IResourceList, IResourceList::FindTranslatedEntry, FindTranslatedEntry
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : portcls.h
req.include-header : Portcls.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IResourceList.FindTranslatedEntry
req.alt-loc : portcls.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# FindTranslatedEntry method
The <code>FindTranslatedEntry</code> method returns a pointer to a translated entry of the specified type, or <b>NULL</b> if no such entry is found.

## Syntax

````
PCM_PARTIAL_RESOURCE_DESCRIPTOR FindTranslatedEntry(
  [in] CM_RESOURCE_TYPE Type,
  [in] ULONG            Index
);
````

## Parameters

`Type`

Identifies the resource type of the entry to find. For a list of valid resource-type values, see the <b>Type</b> member of the <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.

`Index`

Specifies the index of the entry to find. If the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536988">IResourceList::NumberOfEntriesOfType</a> method returns a value <i>n</i> for the number of entries of type <i>Type</i>, valid indices range from 0 to <i>n</i>-1. If <i>Index</i> is zero, for example, the method returns a pointer to the translated version of the first occurrence of an entry of the specified type from the resource list.


## Return Value

<code>FindTranslatedEntry</code> returns a pointer to the specified entry or is <b>NULL</b> if the entry does not exist. This pointer remains valid until the resource list object is deleted.

## Remarks

For each resource type, a macro is defined to call this method. See <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>.

The <i>Index</i> parameter indicates which occurrence of an entry of the specified type to find in the list of translated resource entries. The first occurrence in the list has an index of zero.

For more information about translated and untranslated (or "raw") resources, see <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | portcls.h (include Portcls.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536988">IResourceList::NumberOfEntriesOfType</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536984">IResourceList::FindUntranslatedEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IResourceList::FindTranslatedEntry method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>