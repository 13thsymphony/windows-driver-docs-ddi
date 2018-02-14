---
UID: NF:portcls.IResourceList.NumberOfEntries
title: IResourceList::NumberOfEntries method
author: windows-driver-content
description: The NumberOfEntries method returns the number of resource items in the resource list.
old-location: audio\iresourcelist_numberofentries.htm
old-project: audio
ms.assetid: cb882170-5c8e-455d-89a6-b09ca77e63fb
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.iresourcelist_numberofentries, NumberOfEntries, IResourceList, NumberOfEntries method [Audio Devices], IResourceList interface, NumberOfEntries method [Audio Devices], IResourceList::NumberOfEntries, IResourceList interface [Audio Devices], NumberOfEntries method, portcls/IResourceList::NumberOfEntries, audmp-routines_65fc1416-83e5-4cb6-b362-3133affd5448.xml
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
req.lib: portcls.h
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IResourceList.NumberOfEntries
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---


# NumberOfEntries method
The <code>NumberOfEntries</code> method returns the number of resource items in the resource list.

## Syntax

````
ULONG NumberOfEntries(
    None
);
````

## Parameters

This function has no parameters.

## Return Value

<code>NumberOfEntries</code> returns the number of items in the resource list.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | portcls.h |
| **IRQL** | PASSIVE_LEVEL |