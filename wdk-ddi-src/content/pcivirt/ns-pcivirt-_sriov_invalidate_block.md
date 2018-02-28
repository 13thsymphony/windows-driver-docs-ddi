---
UID: NS:pcivirt._SRIOV_INVALIDATE_BLOCK
title: "_SRIOV_INVALIDATE_BLOCK"
author: windows-driver-content
description: Contains the configuration block information. This structure is used in a IOCTL_SRIOV_INVALIDATE_BLOCK request.
old-location: pci\sriov_invalidate_block.htm
old-project: PCI
ms.assetid: 483e6144-9752-4d47-9ed4-7e73bc0a59cc
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSRIOV_INVALIDATE_BLOCK, PCI.sriov_invalidate_block, SRIOV_INVALIDATE_BLOCK, SRIOV_INVALIDATE_BLOCK structure [Buses], _SRIOV_INVALIDATE_BLOCK, pcivirt/SRIOV_INVALIDATE_BLOCK"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pcivirt.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Pcivirt.h
api_name:
-	SRIOV_INVALIDATE_BLOCK
product: Windows
targetos: Windows
req.typenames: SRIOV_INVALIDATE_BLOCK, *PSRIOV_INVALIDATE_BLOCK
---

# _SRIOV_INVALIDATE_BLOCK structure
Contains the configuration block information. This structure is used in a <a href="https://msdn.microsoft.com/b6f0e65f-c8e4-418f-a4b2-a7037368d5a3">IOCTL_SRIOV_INVALIDATE_BLOCK</a> request.

## Syntax
````
typedef struct _SRIOV_INVALIDATE_BLOCK {
  USHORT  VfIndex;
  UINT64  BlockMask;
} SRIOV_INVALIDATE_BLOCK, SRIOV_INVALIDATE_BLOCK;
````

## Members


`BlockMask`

a block of configuration data.

`VfIndex`

Zero-based index of the virtual function (VF) from the first VF exposed by this physical function (PF).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pcivirt.h |

## See Also

<a href="https://msdn.microsoft.com/b6f0e65f-c8e4-418f-a4b2-a7037368d5a3">IOCTL_SRIOV_INVALIDATE_BLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20SRIOV_INVALIDATE_BLOCK structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>