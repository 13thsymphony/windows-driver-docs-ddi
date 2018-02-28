---
UID: NS:iscsiop._ScsiReadCapacity_IN
title: "_ScsiReadCapacity_IN"
author: windows-driver-content
description: The ScsiReadCapacity_IN structure holds the input data for the ScsiReadCapacity method, which is used to send a SCSI read Ccapacity command.
old-location: storage\scsireadcapacity_in.htm
old-project: storage
ms.assetid: 7a9d6f43-88f7-490e-9446-e707b6497a38
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PScsiReadCapacity_IN, PScsiReadCapacity_IN, PScsiReadCapacity_IN structure pointer [Storage Devices], ScsiReadCapacity_IN, ScsiReadCapacity_IN structure [Storage Devices], _ScsiReadCapacity_IN, iscsiop/PScsiReadCapacity_IN, iscsiop/ScsiReadCapacity_IN, storage.scsireadcapacity_in, structs-iSCSI_6363c086-0475-4bd2-bc15-5e49091e710b.xml"
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
-	ScsiReadCapacity_IN
product: Windows
targetos: Windows
req.typenames: ScsiReadCapacity_IN, *PScsiReadCapacity_IN
---

# _ScsiReadCapacity_IN structure
The ScsiReadCapacity_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564890">ScsiReadCapacity</a> method, which is used to send a SCSI read Ccapacity command.

## Syntax
````
typedef struct _ScsiReadCapacity_IN {
  ULONGLONG UniqueSessionId;
  ULONGLONG Lun;
} ScsiReadCapacity_IN, *PScsiReadCapacity_IN;
````

## Members


`Lun`

A 64-bit number that, together with the name of the target, uniquely identifies the logical unit.

`UniqueSessionId`

A 64-bit integer that uniquely identifies the session. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in the <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.

## Remarks
You must implement this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564890">ScsiReadCapacity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



<a href="..\iscsiop\ns-iscsiop-_scsireadcapacity_out.md">ScsiReadCapacity_OUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiReadCapacity_IN structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>