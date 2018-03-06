---
UID: NS:iscsiop._DeleteInitiatorNodeName_IN
title: "_DeleteInitiatorNodeName_IN"
author: windows-driver-content
description: The DeleteInitiatorNodeName_IN structure holds the input data for the DeleteInitiatorNodeName method, which is used to delete an initiator node name.
old-location: storage\deleteinitiatornodename_in.htm
old-project: storage
ms.assetid: 10b6660c-7f48-4717-89d4-d6a5eb6594c8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDeleteInitiatorNodeName_IN, DeleteInitiatorNodeName_IN, DeleteInitiatorNodeName_IN structure [Storage Devices], PDeleteInitiatorNodeName_IN, PDeleteInitiatorNodeName_IN structure pointer [Storage Devices], _DeleteInitiatorNodeName_IN, iscsiop/DeleteInitiatorNodeName_IN, iscsiop/PDeleteInitiatorNodeName_IN, storage.deleteinitiatornodename_in, structs-iSCSI_2b687a5a-17af-4eda-b48f-8e7ca06024f2.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiop.h
api_name:
-	DeleteInitiatorNodeName_IN
product: Windows
targetos: Windows
req.typenames: DeleteInitiatorNodeName_IN, *PDeleteInitiatorNodeName_IN
---

# _DeleteInitiatorNodeName_IN structure
The DeleteInitiatorNodeName_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552500">DeleteInitiatorNodeName</a> method, which is used to delete an initiator node name.

## Syntax
````
typedef struct _DeleteInitiatorNodeName_IN {
  WCHAR DeletedInitiatorName[223 + 1];
} DeleteInitiatorNodeName_IN, *PDeleteInitiatorNodeName_IN;
````

## Members


`DeletedInitiatorName`

The iSCSI initiator node name that is to be deleted.

## Remarks
It is optional that you implement this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="..\iscsiop\ns-iscsiop-_deleteinitiatornodename_out.md">DeleteInitiatorNodeName_OUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552500">DeleteInitiatorNodeName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DeleteInitiatorNodeName_IN structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>