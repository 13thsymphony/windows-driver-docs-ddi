---
UID: NS:iscsiop._AddConnectionToSession_OUT
title: "_AddConnectionToSession_OUT"
author: windows-driver-content
description: The AddConnectionToSession_OUT structure holds output data for the AddConnectionToSession method.
old-location: storage\addconnectiontosession_out.htm
old-project: storage
ms.assetid: 9c7df21b-c7cd-4492-b457-6c2e82286961
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "_AddConnectionToSession_OUT, PAddConnectionToSession_OUT, storage.addconnectiontosession_out, PAddConnectionToSession_OUT structure pointer [Storage Devices], structs-iSCSI_d630117d-61cb-4c93-97c3-2a0c0b13b04c.xml, iscsiop/AddConnectionToSession_OUT, iscsiop/PAddConnectionToSession_OUT, *PAddConnectionToSession_OUT, AddConnectionToSession_OUT, AddConnectionToSession_OUT structure [Storage Devices]"
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
-	AddConnectionToSession_OUT
product: Windows
targetos: Windows
req.typenames: "*PAddConnectionToSession_OUT, AddConnectionToSession_OUT"
---

# _AddConnectionToSession_OUT structure
The AddConnectionToSession_OUT structure holds output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> method.

## Syntax
````
typedef struct _AddConnectionToSession_OUT {
  ULONG     Status;
  ULONGLONG UniqueConnectionId;
} AddConnectionToSession_OUT, *PAddConnectionToSession_OUT;
````

## Members


`Status`

The status of the <b>AddConnectionToSession </b>operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.

`UniqueConnectionId`

A 64-bit integer that uniquely identifies the connection across the entire network.

## Remarks
The iSCSI service requires this method. It is optional that you implement this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563091">MSiSCSI_Operations WMI Class</a>



<a href="..\iscsiop\ns-iscsiop-_addconnectiontosession_in.md">AddConnectionToSession_IN</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AddConnectionToSession_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>