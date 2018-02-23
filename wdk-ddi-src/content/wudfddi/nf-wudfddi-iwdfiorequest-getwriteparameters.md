---
UID: NF:wudfddi.IWDFIoRequest.GetWriteParameters
title: IWDFIoRequest::GetWriteParameters method
author: windows-driver-content
description: The GetWriteParameters method retrieves the request parameters for a write-type request.
old-location: wdf\iwdfiorequest_getwriteparameters.htm
old-project: wdf
ms.assetid: 0627b278-2fd5-4185-8ec9-8b306c6d85a8
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: umdf.iwdfiorequest_getwriteparameters, wdf.iwdfiorequest_getwriteparameters, GetWriteParameters method, IWDFIoRequest interface, wudfddi/IWDFIoRequest::GetWriteParameters, IWDFIoRequest interface, GetWriteParameters method, IWDFIoRequest, UMDFRequestObjectRef_1aa8b098-4652-435b-beb7-5b7be69fd5d0.xml, GetWriteParameters, GetWriteParameters method, IWDFIoRequest::GetWriteParameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoRequest.GetWriteParameters
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# GetWriteParameters method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetWriteParameters</b> method retrieves the request parameters for a write-type request.

## Syntax

````
void  GetWriteParameters(
  [out] SIZE_T   *pSizeInBytes,
  [out] LONGLONG *pllOffset,
  [out] ULONG    *pulKey
);
````

## Parameters

`pSizeInBytes`

A pointer to a variable that receives the size, in bytes, to write. To retrieve the data for writing, the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a> method.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

`pullOffset`



`pulKey`

A pointer to a variable that receives a key that the driver can use to sort the I/O request in a way that the driver determines. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.


## Return Value

None

## Remarks

A call to <b>GetWriteParameters</b> fails if the request type is not a write type.

For devices that support addressing (for example, a disk device), the value that the <i>pllOffset</i> parameter points to is typically the byte offset into the device. For devices that do not support addressing (for example, a serial port), the driver can ignore the value at <i>pllOffset</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::GetWriteParameters method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>