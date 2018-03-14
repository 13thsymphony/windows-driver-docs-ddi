---
UID: NF:portcls.IResourceList.NumberOfEntriesOfType
title: IResourceList::NumberOfEntriesOfType method
author: windows-driver-content
description: The NumberOfEntriesOfType method returns the number of resource items of a given type in the resource list. For each resource type, a macro is defined to call this method as previously described.
old-location: audio\iresourcelist_numberofentriesoftype.htm
old-project: audio
ms.assetid: 61645c17-9278-49e0-a0bf-24a8c52e964d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IResourceList, IResourceList interface [Audio Devices], NumberOfEntriesOfType method, IResourceList::NumberOfEntriesOfType, NumberOfEntriesOfType method [Audio Devices], NumberOfEntriesOfType method [Audio Devices], IResourceList interface, NumberOfEntriesOfType,IResourceList.NumberOfEntriesOfType, audio.iresourcelist_numberofentriesoftype, audmp-routines_eb0c6999-a901-4087-b7bc-12057f91be90.xml, portcls/IResourceList::NumberOfEntriesOfType
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
-	IResourceList.NumberOfEntriesOfType
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# NumberOfEntriesOfType method
The <code>NumberOfEntriesOfType</code> method returns the number of resource items of a given type in the resource list. For each resource type, a macro is defined to call this method as previously described.

## Syntax

````
ULONG NumberOfEntriesOfType(
  [in] CM_RESOURCE_TYPE Type
);
````

## Parameters

`Type`

Identifies the resource type of the entries that are to be counted. For a list of valid resource-type values, see the <b>Type</b> member of the <a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.


## Return Value

<code>NumberOfEntriesOfType</code> returns the number of items of the indicated type in the resource list.

## Remarks

For each resource type, a macro is defined to call this method. See <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>



<a href="..\wudfwdm\ns-wudfwdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IResourceList::NumberOfEntriesOfType method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>