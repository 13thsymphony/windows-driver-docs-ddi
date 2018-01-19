---
UID : NF:wudfddi.IWDFIoRequest.GetDeviceIoControlParameters
title : IWDFIoRequest::GetDeviceIoControlParameters method
author : windows-driver-content
description : The GetDeviceIoControlParameters method retrieves the request parameters for a device I/O control-type request.
old-location : wdf\iwdfiorequest_getdeviceiocontrolparameters.htm
old-project : wdf
ms.assetid : 96de6f7a-da1d-44a6-b1f7-44859312a662
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFIoRequest, IWDFIoRequest::GetDeviceIoControlParameters, GetDeviceIoControlParameters
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
req.alt-api : IWDFIoRequest.GetDeviceIoControlParameters
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


# GetDeviceIoControlParameters method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDeviceIoControlParameters</b> method retrieves the request parameters for a device I/O control-type request.

## Syntax

````
void  GetDeviceIoControlParameters(
  [out] ULONG  *pControlCode,
  [out] SIZE_T *pInBufferSize,
  [out] SIZE_T *pOutBufferSize
);
````

## Parameters

`pControlCode`

A pointer to a variable that receives the control code that identifies the specific operation to be performed.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

`pInBufferSize`

A pointer to a variable that receives the size, in bytes, of the input data buffer for the request. To retrieve the input data buffer, the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a> method.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

`pOutBufferSize`

A pointer to a variable that receives the size, in bytes, of the output data buffer for the request. To retrieve the output data buffer, the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a> method.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.


## Return Value

None

## Remarks

The call to <b>GetDeviceIoControlParameters</b> fails if the request type is not a device I/O control type.

Although the driver can optionally specify <b>NULL</b> for each of the <i>pControlCode</i>, <i>pInBufferSize</i>, and <i>pOutBufferSize</i> parameters, the driver must specify at least one non-<b>NULL</b> parameter for <b>GetDeviceIoControlParameters</b> to execute successfully.

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
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::GetDeviceIoControlParameters method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>