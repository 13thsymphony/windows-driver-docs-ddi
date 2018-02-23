---
UID: NS:iscsiop._MSiSCSI_TargetMappings
title: "_MSiSCSI_TargetMappings"
author: windows-driver-content
description: The MSiSCSI_TargetMappings structure contains a set of logical unit number (LUN) mappings that are associated with an initiator instance.
old-location: storage\msiscsi_targetmappings.htm
old-project: storage
ms.assetid: 6bddeaeb-9913-4c90-b8ac-3a9f7b384b80
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: iscsiop/MSiSCSI_TargetMappings, *PMSiSCSI_TargetMappings, storage.msiscsi_targetmappings, PMSiSCSI_TargetMappings structure pointer [Storage Devices], PMSiSCSI_TargetMappings, iscsiop/PMSiSCSI_TargetMappings, structs-iSCSI_b8a3267a-8bab-4be6-9f3c-4086cc54f0f5.xml, MSiSCSI_TargetMappings, MSiSCSI_TargetMappings structure [Storage Devices], _MSiSCSI_TargetMappings
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
-	MSiSCSI_TargetMappings
product: Windows
targetos: Windows
req.typenames: "*PMSiSCSI_TargetMappings, MSiSCSI_TargetMappings"
---

# _MSiSCSI_TargetMappings structure
The MSiSCSI_TargetMappings structure contains a set of logical unit number (LUN) mappings that are associated with an initiator instance.

## Syntax
````
typedef struct _MSiSCSI_TargetMappings {
  ULONGLONG           UniqueAdapterId;
  ULONG               TargetMappingCount;
  ULONG               Reserved;
  ISCSI_TargetMapping TargetMappings[1];
} MSiSCSI_TargetMappings, *PMSiSCSI_TargetMappings;
````

## Members


`Reserved`

Reserved for Microsoft use only.

`TargetMappingCount`

The number of mappings in the <b>TargetMappings</b> member.

`TargetMappings`

A variable-length array of <a href="..\iscsidef\ns-iscsidef-_iscsi_targetmapping.md">ISCSI_TargetMapping</a> structures, each of which provides a list of LUN mappings that are associated with a particular iSCSI session that is associated with the adapter ID.

`UniqueAdapterId`

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a> structure.

## Remarks
You must implement this class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="..\iscsidef\ns-iscsidef-_iscsi_targetmapping.md">ISCSI_TargetMapping</a>



<a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563147">MSiSCSI_TargetMappings WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_TargetMappings structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>