---
UID: NS:iscsiop._SetGenerationalGuid_OUT
title: "_SetGenerationalGuid_OUT"
author: windows-driver-content
description: The SetGenerationalGuid_OUT structure holds the output data for the SetGenerationalGuid method.
old-location: storage\setgenerationalguid_out.htm
old-project: storage
ms.assetid: 7b697241-6411-4fb0-b633-502233f2d155
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSetGenerationalGuid_OUT, PSetGenerationalGuid_OUT, PSetGenerationalGuid_OUT structure pointer [Storage Devices], SetGenerationalGuid_OUT, SetGenerationalGuid_OUT structure [Storage Devices], _SetGenerationalGuid_OUT, iscsiop/PSetGenerationalGuid_OUT, iscsiop/SetGenerationalGuid_OUT, storage.setgenerationalguid_out, structs-iSCSI_80d71c4a-f542-4b19-9bbe-b1e8e7cc21cd.xml"
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
-	SetGenerationalGuid_OUT
product: Windows
targetos: Windows
req.typenames: SetGenerationalGuid_OUT, *PSetGenerationalGuid_OUT
---

# _SetGenerationalGuid_OUT structure
The SetGenerationalGuid_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565678">SetGenerationalGuid</a> method.

## Syntax
````
typedef struct _SetGenerationalGuid_OUT {
  ULONG Status;
} SetGenerationalGuid_OUT, *PSetGenerationalGuid_OUT;
````

## Members


`Status`

On output, the status of the <b>SetGenerationalGuid</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.

## Remarks
You must implement this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="..\iscsiop\ns-iscsiop-_setgenerationalguid_in.md">SetGenerationalGuid_IN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565678">SetGenerationalGuid</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetGenerationalGuid_OUT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>