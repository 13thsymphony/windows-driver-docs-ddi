---
UID: NF:wudfusb.IWDFUsbTargetDevice.FormatRequestForControlTransfer
title: IWDFUsbTargetDevice::FormatRequestForControlTransfer method
author: windows-driver-content
description: The FormatRequestForControlTransfer method formats an I/O request object for a USB control transfer.
old-location: wdf\iwdfusbtargetdevice_formatrequestforcontroltransfer.htm
old-project: wdf
ms.assetid: 7f75fbaa-06e8-4c4d-b1ee-c89a55889295
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: FormatRequestForControlTransfer method, FormatRequestForControlTransfer method, IWDFUsbTargetDevice interface, FormatRequestForControlTransfer,IWDFUsbTargetDevice.FormatRequestForControlTransfer, IWDFUsbTargetDevice, IWDFUsbTargetDevice interface, FormatRequestForControlTransfer method, IWDFUsbTargetDevice::FormatRequestForControlTransfer, UMDFUSBref_01a86f28-7a72-4d7b-a2f5-1e254fb26192.xml, umdf.iwdfusbtargetdevice_formatrequestforcontroltransfer, wdf.iwdfusbtargetdevice_formatrequestforcontroltransfer, wudfusb/IWDFUsbTargetDevice::FormatRequestForControlTransfer
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFUsbTargetDevice.FormatRequestForControlTransfer
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# FormatRequestForControlTransfer method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatRequestForControlTransfer</b> method formats an I/O request object for a USB control transfer.

## Syntax

````
HRESULT FormatRequestForControlTransfer(
  [in]           IWDFIoRequest        *pRequest,
  [in]           PWINUSB_SETUP_PACKET SetupPacket,
  [in, optional] IWDFMemory           *pMemory,
  [in, optional] PWDFMEMORY_OFFSET    TransferOffset
);
````

## Parameters

`pRequest`

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface for the request object to format.

`SetupPacket`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540313">WINUSB_SETUP_PACKET</a> for the control transfer.

`pMemory`

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface that is used to access the buffer that is used for the control transfer. This parameter is optional.

`TransferOffset`

A pointer to a <a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a> structure that describes the memory offset that is used for the control transfer. This parameter is optional.


## Return Value

<b>FormatRequestForControlTransfer</b> returns one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/7f75fbaa-06e8-4c4d-b1ee-c89a55889295">FormatRequestForControlTransfer</a> successfully formatted an I/O request object. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/7f75fbaa-06e8-4c4d-b1ee-c89a55889295">FormatRequestForControlTransfer</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG </b></dt>
</dl>
</td>
<td width="60%">
The memory offset that the <i>TransferOffset</i> parameter specified was invalid.

</td>
</tr>
</table>

## Remarks

After a UMDF driver calls <b>FormatRequestForControlTransfer</b> to format an I/O request for a control transfer operation, the framework can subsequently send the request to the I/O target.


#### Examples

The following code example is taken from the <a href="http://go.microsoft.com/fwlink/p/?LinkID=256209">wdf_osrfx2_lab</a> sample in the WDK.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    WINUSB_CONTROL_SETUP_PACKET setupPacket;

    ULONG bytesTransferred;

    HRESULT hr = S_OK;

    //
    // Setup the control packet.
    //

    WINUSB_CONTROL_SETUP_PACKET_INIT( &amp;setupPacket,
                                      BmRequestHostToDevice,
                                      BmRequestToDevice,
                                      USBFX2LK_SET_BARGRAPH_DISPLAY,
                                      0,
                                      0 );

    //
    // Issue the request to WinUsb.
    //

    hr = SendControlTransferSynchronously(
                &amp;(setupPacket.WinUsb),
                (PUCHAR) BarGraphState,
                sizeof(BAR_GRAPH_STATE),
                &amp;bytesTransferred
                );
...

HRESULT
CMyDevice::SendControlTransferSynchronously(
    _In_ PWINUSB_SETUP_PACKET SetupPacket,
    _Inout_updates_(BufferLength) PBYTE Buffer,
    _In_ ULONG BufferLength,
    _Out_ PULONG LengthTransferred
    )
{
    HRESULT hr = S_OK;
    IWDFIoRequest *pWdfRequest = NULL;
    IWDFDriver * FxDriver = NULL;
    IWDFMemory * FxMemory = NULL; 
    IWDFRequestCompletionParams * FxComplParams = NULL;
    IWDFUsbRequestCompletionParams * FxUsbComplParams = NULL;

    *LengthTransferred = 0;
    
    hr = m_FxDevice-&gt;CreateRequest( NULL, //pCallbackInterface
                                    NULL, //pParentObject
                                    &amp;pWdfRequest);

    if (SUCCEEDED(hr))
    {
        m_FxDevice-&gt;GetDriver(&amp;FxDriver);

        hr = FxDriver-&gt;CreatePreallocatedWdfMemory( Buffer,
                                                    BufferLength,
                                                    NULL, //pCallbackInterface
                                                    pWdfRequest, //pParetObject
                                                    &amp;FxMemory );
    }

    if (SUCCEEDED(hr))
    {
        hr = m_pIUsbTargetDevice-&gt;FormatRequestForControlTransfer( pWdfRequest,
                                                                   SetupPacket,
                                                                   FxMemory,
                                                                   NULL); //TransferOffset
    }                                                          
      
</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfusb.h (include Wudfusb.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>



<a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a>



<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>



<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>