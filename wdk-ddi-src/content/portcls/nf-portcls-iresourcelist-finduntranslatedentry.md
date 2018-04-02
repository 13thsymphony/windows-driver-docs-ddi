---
UID: NF:portcls.IResourceList.FindUntranslatedEntry
title: IResourceList::FindUntranslatedEntry method
author: windows-driver-content
description: The FindUntranslatedEntry method returns a pointer to an untranslated entry of the specified type, or NULL if no such pointer is found.
old-location: audio\iresourcelist_finduntranslatedentry.htm
old-project: audio
ms.assetid: 3578eb3a-e9c8-4de3-b959-daff9ac7f1a2
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: FindUntranslatedEntry method [Audio Devices], FindUntranslatedEntry method [Audio Devices], IResourceList interface, FindUntranslatedEntry,IResourceList.FindUntranslatedEntry, IResourceList, IResourceList interface [Audio Devices], FindUntranslatedEntry method, IResourceList::FindUntranslatedEntry, audio.iresourcelist_finduntranslatedentry, audmp-routines_d9b98845-63dd-454d-b1de-dd7db8825e27.xml, portcls/IResourceList::FindUntranslatedEntry
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IResourceList.FindUntranslatedEntry
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IResourceList::FindUntranslatedEntry method
The <code>FindUntranslatedEntry</code> method returns a pointer to an untranslated entry of the specified type, or <b>NULL</b> if no such pointer is found.

## Syntax

```
PCM_PARTIAL_RESOURCE_DESCRIPTOR FindUntranslatedEntry(
  CM_RESOURCE_TYPE Type,
  ULONG            Index
);
```

## Parameters

`Type`

Identifies the resource type of the entries that are to be counted. For a list of valid values, see the <b>Type</b> member of the <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.

`Index`

Specifies the index of the entry to find. If the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536988">IResourceList::NumberOfEntriesOfType</a> method returns a value <i>n</i> for the number of entries of type <i>Type</i>, valid indices range from 0 to <i>n</i>-1. If <i>Index</i> is zero, for example, the method returns a pointer to the untranslated version of the first occurrence of an entry of the specified type from the resource list.


## Return Value

<code>FindUntranslatedEntry</code> returns a pointer to the specified entry or is <b>NULL</b> if the entry does not exist. This pointer remains valid until the resource object is deleted.

## Remarks

For each resource type, a macro is defined to call this method. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>.

The <i>Index</i> parameter indicates which occurrence of an entry of the specified type to find in the list of translated resource entries. The first occurrence in the list has an index of zero.

For each resource type, a macro is defined to call this method. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>.

For more information about translated and untranslated (or "raw") resources, see <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536982">IResourceList::FindTranslatedEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536988">IResourceList::NumberOfEntriesOfType</a>