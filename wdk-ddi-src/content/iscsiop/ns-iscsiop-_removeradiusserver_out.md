---
UID: NS:iscsiop._RemoveRADIUSServer_OUT
title: "_RemoveRADIUSServer_OUT"
author: windows-driver-content
description: The RemoveiSNSServer_OUT structure holds the output data for the RemoveRADIUSServer method.
old-location: storage\removeradiusserver_out.htm
old-project: storage
ms.assetid: da5be900-a362-4d74-9ac7-65b96f0348ce
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PRemoveRADIUSServer_OUT structure pointer [Storage Devices], storage.removeradiusserver_out, *PRemoveRADIUSServer_OUT, iscsiop/PRemoveRADIUSServer_OUT, RemoveRADIUSServer_OUT structure [Storage Devices], iscsiop/RemoveRADIUSServer_OUT, structs-iSCSI_dea5813a-b7e8-4702-af57-f7a40360efb9.xml, _RemoveRADIUSServer_OUT, PRemoveRADIUSServer_OUT, RemoveRADIUSServer_OUT
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
-	RemoveRADIUSServer_OUT
product: Windows
targetos: Windows
req.typenames: "*PRemoveRADIUSServer_OUT, RemoveRADIUSServer_OUT"
---

# _RemoveRADIUSServer_OUT structure
The RemoveiSNSServer_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564020">RemoveRADIUSServer</a> method.

## Syntax
````
typedef struct _RemoveRADIUSServer_OUT {
  ULONG Status;
} RemoveRADIUSServer_OUT, *PRemoveRADIUSServer_OUT;
````

## Members


`Status`

On output from <b>RemoveRADIUSServer</b>, the status of the operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.

## Remarks
It is optional that you implement this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="..\iscsiop\ns-iscsiop-_removeradiusserver_in.md">RemoveRADIUSServer_IN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564020">RemoveRADIUSServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemoveRADIUSServer_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>