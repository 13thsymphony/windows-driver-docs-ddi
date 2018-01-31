---
UID : NF:wudfusb.IWDFUsbInterface.RetrieveUsbPipeObject
title : IWDFUsbInterface::RetrieveUsbPipeObject method
author : windows-driver-content
description : The RetrieveUsbPipeObject method retrieves a USB pipe object for the specified pipe index.
old-location : wdf\iwdfusbinterface_retrieveusbpipeobject.htm
old-project : wdf
ms.assetid : abfaad6b-be42-4547-aa26-5b44e53118bc
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFUsbInterface::RetrieveUsbPipeObject, RetrieveUsbPipeObject method, IWDFUsbInterface interface, IWDFUsbInterface interface, RetrieveUsbPipeObject method, wudfusb/IWDFUsbInterface::RetrieveUsbPipeObject, wdf.iwdfusbinterface_retrieveusbpipeobject, UMDFUSBref_84f2ac72-965e-4fd4-a127-f153a5fc54f7.xml, RetrieveUsbPipeObject method, RetrieveUsbPipeObject, IWDFUsbInterface, umdf.iwdfusbinterface_retrieveusbpipeobject
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
req.typenames : WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product : Windows 10 or later.
---


# RetrieveUsbPipeObject method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveUsbPipeObject</b> method retrieves a USB pipe object for the specified pipe index.

## Syntax

````
HRESULT RetrieveUsbPipeObject(
  [in]  UCHAR             PipeIndex,
  [out] IWDFUsbTargetPipe **ppPipe
);
````

## Parameters

`PipeIndex`

The index of the USB pipe object to retrieve.

`ppPipe`

A pointer to a variable that receives a pointer to the <a href="..\wudfusb\nn-wudfusb-iwdfusbtargetpipe.md">IWDFUsbTargetPipe</a> interface for the USB pipe object whose index is specified by <i>PipeIndex</i>.


## Return Value

<b>RetrieveUsbPipeObject</b> returns one of the following values: 
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

<a href="https://msdn.microsoft.com/abfaad6b-be42-4547-aa26-5b44e53118bc">RetrieveUsbPipeObject</a> successfully retrieved the USB pipe object. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/abfaad6b-be42-4547-aa26-5b44e53118bc">RetrieveUsbPipeObject</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>
</td>
<td width="60%">
This value corresponds to the error code that the WinUsb API returned.

</td>
</tr>
</table>

## Remarks

A UMDF driver can call the methods of the <a href="..\wudfusb\nn-wudfusb-iwdfusbtargetpipe.md">IWDFUsbTargetPipe</a> interface that the <b>RetrieveUsbPipeObject</b> method retrieves to obtain the type of pipe and other information.

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

<a href="..\wudfusb\nn-wudfusb-iwdfusbinterface.md">IWDFUsbInterface</a>

<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetpipe.md">IWDFUsbTargetPipe</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbInterface::RetrieveUsbPipeObject method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>