---
UID: NF:portcls.IResourceList.FindTranslatedEntry
title: IResourceList::FindTranslatedEntry method
author: windows-driver-content
description: The FindTranslatedEntry method returns a pointer to a translated entry of the specified type, or NULL if no such entry is found.
old-location: audio\iresourcelist_findtranslatedentry.htm
old-project: audio
ms.assetid: b3e8ae4d-a923-406e-ad1a-f7ed7277f676
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: FindTranslatedEntry method [Audio Devices], FindTranslatedEntry method [Audio Devices], IResourceList interface, FindTranslatedEntry,IResourceList.FindTranslatedEntry, IResourceList, IResourceList interface [Audio Devices], FindTranslatedEntry method, IResourceList::FindTranslatedEntry, audio.iresourcelist_findtranslatedentry, audmp-routines_a4100c1c-8955-46bb-a9cc-8cee22609598.xml, portcls/IResourceList::FindTranslatedEntry
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
-	IResourceList.FindTranslatedEntry
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IResourceList::FindTranslatedEntry method
The <code>FindTranslatedEntry</code> method returns a pointer to a translated entry of the specified type, or <b>NULL</b> if no such entry is found.

## Syntax

```
PCM_PARTIAL_RESOURCE_DESCRIPTOR FindTranslatedEntry(
  CM_RESOURCE_TYPE Type,
  ULONG            Index
);
```

## Parameters

`Type`

Identifies the resource type of the entry to find. For a list of valid resource-type values, see the <b>Type</b> member of the <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.

`Index`

Specifies the index of the entry to find. If the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536988">IResourceList::NumberOfEntriesOfType</a> method returns a value <i>n</i> for the number of entries of type <i>Type</i>, valid indices range from 0 to <i>n</i>-1. If <i>Index</i> is zero, for example, the method returns a pointer to the translated version of the first occurrence of an entry of the specified type from the resource list.


## Return Value

<code>FindTranslatedEntry</code> returns a pointer to the specified entry or is <b>NULL</b> if the entry does not exist. This pointer remains valid until the resource list object is deleted.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536984">IResourceList::FindUntranslatedEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536988">IResourceList::NumberOfEntriesOfType</a>