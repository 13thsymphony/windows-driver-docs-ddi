---
UID: NE:ndkpi._NDK_OPERATION_TYPE
title: "_NDK_OPERATION_TYPE"
author: windows-driver-content
description: The NDK_OPERATION_TYPE enumeration defines types of NDK operations. Its enumeration values are used in the Type member of the NDK_RESULT_EX structure.
old-location: netvista\ndk_operation_type.htm
old-project: netvista
ms.assetid: EBB89BDA-6249-4D0F-A0EE-7074DDAFFFC1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDK_OPERATION_TYPE, NDK_OPERATION_TYPE enumeration [Network Drivers Starting with Windows Vista], NdkOperationTypeBind, NdkOperationTypeFastRegister, NdkOperationTypeInvalidate, NdkOperationTypeRead, NdkOperationTypeReceive, NdkOperationTypeReceiveAndInvalidate, NdkOperationTypeSend, NdkOperationTypeWrite, _NDK_OPERATION_TYPE, ndkpi/NDK_OPERATION_TYPE, ndkpi/NdkOperationTypeBind, ndkpi/NdkOperationTypeFastRegister, ndkpi/NdkOperationTypeInvalidate, ndkpi/NdkOperationTypeRead, ndkpi/NdkOperationTypeReceive, ndkpi/NdkOperationTypeReceiveAndInvalidate, ndkpi/NdkOperationTypeSend, ndkpi/NdkOperationTypeWrite, netvista.ndk_operation_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.40 and later.
req.target-min-winversvr: Windows Server 2012 R2
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndkpi.h
api_name:
-	NDK_OPERATION_TYPE
product: Windows
targetos: Windows
req.typenames: NDK_OPERATION_TYPE
---

# _NDK_OPERATION_TYPE Enumeration
The <b>NDK_OPERATION_TYPE</b> enumeration defines types of NDK operations. Its enumeration values are used in the <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265509">NDK_RESULT_EX</a> structure.

## Syntax
```
typedef enum _NDK_OPERATION_TYPE {
  NdkOperationTypeReceive               ,
  NdkOperationTypeReceiveAndInvalidate  ,
  NdkOperationTypeSend                  ,
  NdkOperationTypeFastRegister          ,
  NdkOperationTypeBind                  ,
  NdkOperationTypeInvalidate            ,
  NdkOperationTypeRead                  ,
  NdkOperationTypeWrite
} NDK_OPERATION_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>NdkOperationTypeReceive</td>
                    <td>An <i>NdkReceive</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439907">NDK_FN_RECEIVE</a>) operation.</td>
                </tr>
            
                <tr>
                    <td>NdkOperationTypeReceiveAndInvalidate</td>
                    <td>An <i>NdkSendAndInvalidate</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/dn265507">NDK_FN_SEND_AND_INVALIDATE</a>) operation.</td>
                </tr>
            
                <tr>
                    <td>NdkOperationTypeSend</td>
                    <td>An <i>NdkSend</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439914">NDK_FN_SEND</a>) operation.</td>
                </tr>
            
                <tr>
                    <td>NdkOperationTypeFastRegister</td>
                    <td>An <i>NdkFastRegister</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439887">NDK_FN_FAST_REGISTER</a>) operation.</td>
                </tr>
            
                <tr>
                    <td>NdkOperationTypeBind</td>
                    <td>An <i>NdkBind</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439859">NDK_FN_BIND</a>)  operation.</td>
                </tr>
            
                <tr>
                    <td>NdkOperationTypeInvalidate</td>
                    <td>An <i>NdkInvalidate</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439901">NDK_FN_INVALIDATE</a>) operation.</td>
                </tr>
            
                <tr>
                    <td>NdkOperationTypeRead</td>
                    <td>An <i>NdkRead</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439906">NDK_FN_READ</a>) operation.</td>
                </tr>
            
                <tr>
                    <td>NdkOperationTypeWrite</td>
                    <td>An <i>NdkWrite</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439917">NDK_FN_WRITE</a>) operation.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.40 and later. None supported,Supported in NDIS 6.40 and later. |
| **Header** | ndkpi.h (include Ndkpi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265509">NDK_RESULT_EX</a>