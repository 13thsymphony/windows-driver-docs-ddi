---
UID: NS:ndkpi._NDK_MR
title: "_NDK_MR"
author: windows-driver-content
description: The NDK_MR structure specifies the attributes of an NDK memory region (MR) object.
old-location: netvista\ndk_mr.htm
old-project: netvista
ms.assetid: F0585210-048E-4397-98E4-46640731E66C
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PNDK_MR structure pointer [Network Drivers Starting with Windows Vista], netvista.ndk_mr, ndkpi/NDK_MR, _NDK_MR, NDK_MR, PNDK_MR, ndkpi/PNDK_MR, NDK_MR structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndkpi.h
apiname:
-	NDK_MR
product: Windows
targetos: Windows
req.typenames: NDK_MR
---

# _NDK_MR structure
The <b>NDK_MR</b> structure specifies the attributes of an NDK memory region (MR) object.

## Syntax
````
typedef struct _NDK_MR {
  NDK_OBJECT_HEADER     Header;
  CONST NDK_MR_DISPATCH *Dispatch;
} NDK_MR, *PNDK_MR;
````

## Members


`Dispatch`

A pointer to an <a href="..\ndkpi\ns-ndkpi-_ndk_mr_dispatch.md">NDK_MR_DISPATCH</a> structure that defines dispatch functions for the NDK MR object.

`Header`

The <a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a> structure for the <b>NDK_MR</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeMr</b>.

## Remarks
An NDK provider must set the <b>Dispatch</b> member to point to its  <a href="..\ndkpi\ns-ndkpi-_ndk_mr_dispatch.md">NDK_MR_DISPATCH</a> table before returning the  created MR object. Also, the NDK provider must not use the <b>Dispatch</b> member after setting it because the NDK consumer can change the <b>Dispatch</b> member to some other value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.30 and later. None supported,Supported in NDIS 6.30 and later. |
| **Header** | ndkpi.h (include Ndkpi.h) |

## See Also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_mr.md">NDK_FN_CREATE_MR</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_mr_dispatch.md">NDK_MR_DISPATCH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_MR structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>