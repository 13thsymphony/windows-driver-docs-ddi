---
UID: NS:iscsiop._RemovePersistentLogin_OUT
title: "_RemovePersistentLogin_OUT"
author: windows-driver-content
description: The RemovePersistentLogin_OUT structure holds the output data for the RemovePersistentLogin method.
old-location: storage\removepersistentlogin_out.htm
old-project: storage
ms.assetid: 2b5aee65-ccf6-42c6-9bb3-dff93cb53cf0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: structs-iSCSI_59f0b686-33c3-47be-9bd7-89d14f3ffc7b.xml, iscsiop/RemovePersistentLogin_OUT, *PRemovePersistentLogin_OUT, iscsiop/PRemovePersistentLogin_OUT, RemovePersistentLogin_OUT, RemovePersistentLogin_OUT structure [Storage Devices], storage.removepersistentlogin_out, PRemovePersistentLogin_OUT structure pointer [Storage Devices], _RemovePersistentLogin_OUT, PRemovePersistentLogin_OUT
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
-	RemovePersistentLogin_OUT
product: Windows
targetos: Windows
req.typenames: "*PRemovePersistentLogin_OUT, RemovePersistentLogin_OUT"
---

# _RemovePersistentLogin_OUT structure
The RemovePersistentLogin_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563995">RemovePersistentLogin</a> method.

## Syntax
````
typedef struct _RemovePersistentLogin_OUT {
  ULONG Status;
} RemovePersistentLogin_OUT, *PRemovePersistentLogin_OUT;
````

## Members


`Status`

On output from <b>RemovePersistentLogin</b>, the status of the operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.

## Remarks
You must implement this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="..\iscsiop\ns-iscsiop-_removepersistentlogin_in.md">RemovePersistentLogin_IN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563995">RemovePersistentLogin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemovePersistentLogin_OUT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>