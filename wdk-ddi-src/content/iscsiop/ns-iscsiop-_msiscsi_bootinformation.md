---
UID: NS:iscsiop._MSiSCSI_BootInformation
title: "_MSiSCSI_BootInformation"
author: windows-driver-content
description: The MSiSCSI_BootInformation structure is used with the MSiSCSI_BootInformation WMI Class to expose information about the node that contains the target boot device.
old-location: storage\msiscsi_bootinformation.htm
old-project: storage
ms.assetid: 971bbd30-5bde-4cf6-9b94-7c21c29590d5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMSiSCSI_BootInformation, MSiSCSI_BootInformation, MSiSCSI_BootInformation structure [Storage Devices], PMSiSCSI_BootInformation, PMSiSCSI_BootInformation structure pointer [Storage Devices], _MSiSCSI_BootInformation, iscsiop/MSiSCSI_BootInformation, iscsiop/PMSiSCSI_BootInformation, storage.msiscsi_bootinformation, structs-iSCSI_a33678de-f559-4c7a-8007-55ab0381b613.xml"
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
-	MSiSCSI_BootInformation
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_BootInformation, *PMSiSCSI_BootInformation
---

# _MSiSCSI_BootInformation structure
The MSiSCSI_BootInformation structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562984">MSiSCSI_BootInformation WMI Class</a> to expose information about the node that contains the target boot device.

## Syntax
```
typedef struct _MSiSCSI_BootInformation {
  UCHAR NodeName[223];
  ULONG SharedSecretLength;
  UCHAR SharedSecret[255];
} MSiSCSI_BootInformation, *PMSiSCSI_BootInformation;
```

## Members


`NodeName`

The name of the initiator node that contains the boot device.

`SharedSecretLength`

The length, in bytes, of the shared secret for the initiator node.

`SharedSecret`

The shared secret for the initiator node.

## Remarks
You must implement this class if the adapter supports iSCSI boot.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="https://msdn.microsoft.com/a6ed673a-b5c1-4857-803a-4f0f3cf798d8">MSiSCSI_BootInformationWMI Class</a>