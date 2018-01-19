---
UID : NF:wudfddi.IWDFIoRequestCompletionParams.GetWriteParameters
title : IWDFIoRequestCompletionParams::GetWriteParameters method
author : windows-driver-content
description : The GetWriteParameters method retrieves parameters that are associated with the completion of a write request.
old-location : wdf\iwdfiorequestcompletionparams_getwriteparameters.htm
old-project : wdf
ms.assetid : 7161ba67-d94a-4f05-bb8f-a97ef418e580
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFIoRequestCompletionParams, IWDFIoRequestCompletionParams::GetWriteParameters, GetWriteParameters
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfddi.h
req.include-header : Wudfddi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.5
req.alt-api : IWDFIoRequestCompletionParams.GetWriteParameters
req.alt-loc : WUDFx.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : WUDFx.dll
req.irql : 
req.typenames : "*PPOWER_ACTION, POWER_ACTION"
req.product : Windows 10 or later.
---


# GetWriteParameters method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetWriteParameters</b> method retrieves parameters that are associated with the completion of a write request.

## Syntax

````
void  GetWriteParameters(
  [out] IWDFMemory **ppWriteMemory,
  [out] SIZE_T     pBytesWritten,
  [out] SIZE_T     pWriteMemoryOffset
);
````

## Parameters

`ppWriteMemory`

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface for access to the write buffer for the completion of the write request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

`pBytesWritten`

A pointer to a variable that receives the size, in bytes, of the write buffer for the completion of the write request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

`pWriteMemoryOffset`

A pointer to a variable that receives the offset, in bytes, into the write buffer for the completion of the write request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfiorequestcompletionparams.md">IWDFIoRequestCompletionParams</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequestCompletionParams::GetWriteParameters method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>