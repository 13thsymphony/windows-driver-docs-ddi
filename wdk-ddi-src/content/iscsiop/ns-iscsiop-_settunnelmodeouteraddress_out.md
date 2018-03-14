---
UID: NS:iscsiop._SetTunnelModeOuterAddress_OUT
title: "_SetTunnelModeOuterAddress_OUT"
author: windows-driver-content
description: The SetTunnelModeOuterAddress_OUT structure holds the output data for the SetTunnelModeOuterAddress method.
old-location: storage\settunnelmodeouteraddress_out.htm
old-project: storage
ms.assetid: 2cfe935f-eba4-48aa-869d-6381ca038e70
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSetTunnelModeOuterAddress_OUT, PSetTunnelModeOuterAddress_OUT, PSetTunnelModeOuterAddress_OUT structure pointer [Storage Devices], SetTunnelModeOuterAddress_OUT, SetTunnelModeOuterAddress_OUT structure [Storage Devices], _SetTunnelModeOuterAddress_OUT, iscsiop/PSetTunnelModeOuterAddress_OUT, iscsiop/SetTunnelModeOuterAddress_OUT, storage.settunnelmodeouteraddress_out, structs-iSCSI_918f9bb3-ee9f-41d3-8e9e-c18a673a4302.xml"
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
-	SetTunnelModeOuterAddress_OUT
product: Windows
targetos: Windows
req.typenames: SetTunnelModeOuterAddress_OUT, *PSetTunnelModeOuterAddress_OUT
---

# _SetTunnelModeOuterAddress_OUT structure
The SetTunnelModeOuterAddress_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566186">SetTunnelModeOuterAddress</a> method.

## Syntax
````
typedef struct _SetTunnelModeOuterAddress_OUT {
  ULONG Status;
} SetTunnelModeOuterAddress_OUT, *PSetTunnelModeOuterAddress_OUT;
````

## Members


`Status`

On output, the status of the <b>SetTunnelModeOuterAddress</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.

## Remarks
You must implement this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566186">SetTunnelModeOuterAddress</a>



<a href="..\iscsiop\ns-iscsiop-_settunnelmodeouteraddress_in.md">SetTunnelModeOuterAddress_IN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetTunnelModeOuterAddress_OUT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>