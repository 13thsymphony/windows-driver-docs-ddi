---
UID: NS:iscsimgt._SetLoadBalancePolicy_OUT
title: "_SetLoadBalancePolicy_OUT"
author: windows-driver-content
description: The SetLoadBalancePolicy_OUT structure holds the output data for the SetLoadBalance method.
old-location: storage\setloadbalancepolicy_out.htm
old-project: storage
ms.assetid: 28b54f80-9268-4ccb-ac19-b1b4bfef4192
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSetLoadBalancePolicy_OUT, PSetLoadBalancePolicy_OUT, PSetLoadBalancePolicy_OUT structure pointer [Storage Devices], SetLoadBalancePolicy_OUT, SetLoadBalancePolicy_OUT structure [Storage Devices], _SetLoadBalancePolicy_OUT, iscsimgt/PSetLoadBalancePolicy_OUT, iscsimgt/SetLoadBalancePolicy_OUT, storage.setloadbalancepolicy_out, structs-iSCSI_32a19db4-8102-4e39-b9be-30a8a03d2732.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsimgt.h
req.include-header: Iscsimgt.h
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
-	iscsimgt.h
api_name:
-	SetLoadBalancePolicy_OUT
product: Windows
targetos: Windows
req.typenames: SetLoadBalancePolicy_OUT, *PSetLoadBalancePolicy_OUT
---

# _SetLoadBalancePolicy_OUT structure
The SetLoadBalancePolicy_OUT structure holds the output data for the SetLoadBalance method.

## Syntax
````
typedef struct _SetLoadBalancePolicy_OUT {
  ULONG Status;
} SetLoadBalancePolicy_OUT, *PSetLoadBalancePolicy_OUT;
````

## Members


`Status`

A value that provides the status of the SetLoadBalancePolicy operation.

## Remarks
You must implement this class. For a list of possible status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsimgt.h (include Iscsimgt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563062">MSiSCSI_LB_Operations WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetLoadBalancePolicy_OUT structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>