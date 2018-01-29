---
UID : NF:wudfusb.IWDFUsbRequestCompletionParams.GetDeviceControlTransferParameters
title : IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters method
author : windows-driver-content
description : The GetDeviceControlTransferParameters method retrieves parameters that are associated with the completion of a device I/O control request.
old-location : wdf\iwdfusbrequestcompletionparams_getdevicecontroltransferparameters.htm
old-project : wdf
ms.assetid : 0c3fd576-48de-454b-8015-51767b21f17e
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFUsbRequestCompletionParams, wudfusb/IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters, IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters, UMDFRequestObjectRef_b645716e-2ec3-45f3-a3b2-199374aadef8.xml, IWDFUsbRequestCompletionParams interface, GetDeviceControlTransferParameters method, wdf.iwdfusbrequestcompletionparams_getdevicecontroltransferparameters, GetDeviceControlTransferParameters method, GetDeviceControlTransferParameters method, IWDFUsbRequestCompletionParams interface, GetDeviceControlTransferParameters, umdf.iwdfusbrequestcompletionparams_getdevicecontroltransferparameters
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfusb.h
req.include-header : Wudfusb.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.5
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : wudfusb.h
req.dll : WUDFx.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product : Windows 10 or later.
---


# GetDeviceControlTransferParameters method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDeviceControlTransferParameters</b> method retrieves parameters that are associated with the completion of a device I/O control request.

## Syntax

````
void GetDeviceControlTransferParameters(
  [out, optional] IWDFMemory           **ppMemory,
  [out, optional] ULONG                *pLengthTransferred,
  [out, optional] SIZE_T               *pOffset,
  [out, optional] PWINUSB_SETUP_PACKET pSetupPacket
);
````

## Parameters

`ppMemory`

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface, for access to the buffer for the device I/O control request. This parameter is optional and can be <b>NULL</b>.

`pLengthTransferred`

A pointer to a variable that receives the size, in bytes, of transferred data. This parameter is optional and can be <b>NULL</b>.

`pOffset`

A pointer to a variable that receives the offset, in bytes, into the buffer for the I/O control request. This parameter is optional and can be <b>NULL</b>.

`pSetupPacket`

A pointer that receives the WinUsb setup packet for the control transfer. This pointer is a PWINUSB_SETUP_PACKET data type that is defined as PVOID. This parameter is optional and can be <b>NULL</b>.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfusb.h (include Wudfusb.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\wudfusb\nn-wudfusb-iwdfusbrequestcompletionparams.md">IWDFUsbRequestCompletionParams</a>

<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>