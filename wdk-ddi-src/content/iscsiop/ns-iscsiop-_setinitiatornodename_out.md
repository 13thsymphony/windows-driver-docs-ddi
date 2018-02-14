---
UID: NS:iscsiop._SetInitiatorNodeName_OUT
title: "_SetInitiatorNodeName_OUT"
author: windows-driver-content
description: The SetInitiatorNodeName_OUT structure holds the output data for the SetInitiatorNodeName method.
old-location: storage\setinitiatornodename_out.htm
old-project: storage
ms.assetid: f3417648-f9f9-402f-b3a3-d09c0b7e5fdd
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: iscsiop/SetInitiatorNodeName_OUT, *PSetInitiatorNodeName_OUT, PSetInitiatorNodeName_OUT structure pointer [Storage Devices], storage.setinitiatornodename_out, structs-iSCSI_35ce4900-1703-4562-abe0-155215893c5f.xml, PSetInitiatorNodeName_OUT, iscsiop/PSetInitiatorNodeName_OUT, SetInitiatorNodeName_OUT structure [Storage Devices], _SetInitiatorNodeName_OUT, SetInitiatorNodeName_OUT
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsiop.h
apiname:
-	SetInitiatorNodeName_OUT
product: Windows
targetos: Windows
req.typenames: SetInitiatorNodeName_OUT, *PSetInitiatorNodeName_OUT
---

# _SetInitiatorNodeName_OUT structure
The SetInitiatorNodeName_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565706">SetInitiatorNodeName</a> method.

## Syntax
````
typedef struct _SetInitiatorNodeName_OUT {
  ULONG Status;
} SetInitiatorNodeName_OUT, *PSetInitiatorNodeName_OUT;
````

## Members


`Status`

On output, the status of the <b>SetInitiatorNodeName</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.

## Remarks
It is optional that you implement this class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565706">SetInitiatorNodeName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="..\iscsiop\ns-iscsiop-_setinitiatornodename_in.md">SetInitiatorNodeName_IN</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetInitiatorNodeName_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>