---
UID: NS:iscsiop._AddConnectionToSession_OUT
title: "_AddConnectionToSession_OUT"
author: windows-driver-content
description: The AddConnectionToSession_OUT structure holds output data for the AddConnectionToSession method.
old-location: storage\addconnectiontosession_out.htm
old-project: storage
ms.assetid: 9c7df21b-c7cd-4492-b457-6c2e82286961
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PAddConnectionToSession_OUT, AddConnectionToSession_OUT, AddConnectionToSession_OUT structure [Storage Devices], PAddConnectionToSession_OUT, PAddConnectionToSession_OUT structure pointer [Storage Devices], _AddConnectionToSession_OUT, iscsiop/AddConnectionToSession_OUT, iscsiop/PAddConnectionToSession_OUT, storage.addconnectiontosession_out, structs-iSCSI_d630117d-61cb-4c93-97c3-2a0c0b13b04c.xml"
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
-	AddConnectionToSession_OUT
product:
- Windows
targetos: Windows
req.typenames: AddConnectionToSession_OUT, *PAddConnectionToSession_OUT
---

# _AddConnectionToSession_OUT structure
The AddConnectionToSession_OUT structure holds output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> method.

## Syntax
```
typedef struct _AddConnectionToSession_OUT {
  ULONG     Status;
  ULONGLONG UniqueConnectionId;
} *PAddConnectionToSession_OUT, AddConnectionToSession_OUT;
```

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550122">AddConnectionToSession_IN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563091">MSiSCSI_Operations WMI Class</a>