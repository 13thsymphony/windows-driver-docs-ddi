---
UID: NF:wudfusb.IWDFUsbTargetDevice.FormatRequestForControlTransfer
title: IWDFUsbTargetDevice::FormatRequestForControlTransfer method
author: windows-driver-content
description: The FormatRequestForControlTransfer method formats an I/O request object for a USB control transfer.
old-location: wdf\iwdfusbtargetdevice_formatrequestforcontroltransfer.htm
old-project: wdf
ms.assetid: 7f75fbaa-06e8-4c4d-b1ee-c89a55889295
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFUsbTargetDevice, IWDFUsbTargetDevice::FormatRequestForControlTransfer, FormatRequestForControlTransfer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFUsbTargetDevice.FormatRequestForControlTransfer
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbTargetDevice::FormatRequestForControlTransfer method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatRequestForControlTransfer</b> method formats an I/O request object for a USB control transfer.



## -syntax

````
HRESULT FormatRequestForControlTransfer(
  [in]           IWDFIoRequest        *pRequest,
  [in]           PWINUSB_SETUP_PACKET SetupPacket,
  [in, optional] IWDFMemory           *pMemory,
  [in, optional] PWDFMEMORY_OFFSET    TransferOffset
);
````


## -parameters

### -param pRequest [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface for the request object to format. 


### -param SetupPacket [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540313">WINUSB_SETUP_PACKET</a> for the control transfer.


### -param pMemory [in, optional]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface that is used to access the buffer that is used for the control transfer. This parameter is optional.


### -param TransferOffset [in, optional]

A pointer to a <a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a> structure that describes the memory offset that is used for the control transfer. This parameter is optional.


## -returns
<b>FormatRequestForControlTransfer</b> returns one of the following values: 
<dl>
<dt><b>S_OK </b></dt>
</dl>
<a href="https://msdn.microsoft.com/7f75fbaa-06e8-4c4d-b1ee-c89a55889295">FormatRequestForControlTransfer</a> successfully formatted an I/O request object. 
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
<a href="https://msdn.microsoft.com/7f75fbaa-06e8-4c4d-b1ee-c89a55889295">FormatRequestForControlTransfer</a> encountered an allocation failure.
<dl>
<dt><b>E_INVALIDARG </b></dt>
</dl>The memory offset that the <i>TransferOffset</i> parameter specified was invalid.

 


## -remarks
After a UMDF driver calls <b>FormatRequestForControlTransfer</b> to format an I/O request for a control transfer operation, the framework can subsequently send the request to the I/O target.

The following code example is taken from the <a href="http://go.microsoft.com/fwlink/p/?LinkID=256209">wdf_osrfx2_lab</a> sample in the WDK.


## -see-also
<dl>
<dt>
<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>
</dt>
<dt>
<a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetDevice::FormatRequestForControlTransfer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

