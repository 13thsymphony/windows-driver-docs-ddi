---
UID: NS:iscsiop._RemoveiSNSServer_OUT
title: "_RemoveiSNSServer_OUT"
author: windows-driver-content
description: The RemoveiSNSServer_OUT structure holds the output data for the user-mode RemoveISNSServer method.
old-location: storage\removeisnsserver_out.htm
old-project: storage
ms.assetid: 42866b25-280c-492c-8e98-1a04a46561a4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PRemoveiSNSServer_OUT, PRemoveiSNSServer_OUT, PRemoveiSNSServer_OUT structure pointer [Storage Devices], RemoveiSNSServer_OUT, RemoveiSNSServer_OUT structure [Storage Devices], _RemoveiSNSServer_OUT, iscsiop/PRemoveiSNSServer_OUT, iscsiop/RemoveiSNSServer_OUT, storage.removeisnsserver_out, structs-iSCSI_8d8df1a1-3b89-42a1-9ef8-3e749a94b531.xml"
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
-	RemoveiSNSServer_OUT
product: Windows
targetos: Windows
req.typenames: RemoveiSNSServer_OUT, *PRemoveiSNSServer_OUT
---

# _RemoveiSNSServer_OUT structure
The RemoveiSNSServer_OUT structure holds the output data for the user-mode <b>RemoveISNSServer</b> method.

## Syntax
````
typedef struct _RemoveiSNSServer_OUT {
  ULONG Status;
} RemoveiSNSServer_OUT, *PRemoveiSNSServer_OUT;
````

## Members


`Status`

On output from <b>RemoveISNSServer</b>, the status of the operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.

## Remarks
It is optional that you implement this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="..\iscsiop\ns-iscsiop-_removeisnsserver_in.md">RemoveiSNSServer_IN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemoveiSNSServer_OUT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>