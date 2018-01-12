---
UID: NF:wudfddi.IWDFIoRequest2.GetEffectiveIoType
title: IWDFIoRequest2::GetEffectiveIoType method
author: windows-driver-content
description: The GetEffectiveIoType method returns the buffer access method that UMDF is using for the data buffers of the I/O request that the IWDFIoRequest2 interface represents.
old-location: wdf\iwdfiorequest2_geteffectiveiotype.htm
old-project: wdf
ms.assetid: 76909efd-99ca-4e47-9c81-8a48608c2543
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IWDFIoRequest2, IWDFIoRequest2::GetEffectiveIoType, GetEffectiveIoType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IWDFIoRequest2.GetEffectiveIoType
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
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest2::GetEffectiveIoType method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetEffectiveIoType</b> method returns the buffer access method that UMDF is using for the data buffers of the I/O request that the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a> interface represents.



## -syntax

````
WDF_DEVICE_IO_TYPE GetEffectiveIoType();
````


## -parameters


## -returns
<b>GetEffectiveIoType</b> returns a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>-typed value that identifies the buffer access method that UMDF is using for the I/O request's data buffers. 

<b>GetEffectiveIoType</b> returns a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>-typed value that identifies the buffer access method that UMDF is using for the I/O request's data buffers. 

<b>GetEffectiveIoType</b> returns a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>-typed value that identifies the buffer access method that UMDF is using for the I/O request's data buffers. 


## -remarks
For more information about accessing data buffers and when your driver should use <b>GetEffectiveIoType</b>, see <a href="wdf.accessing_data_buffers_in_umdf_drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.

The following code example shows how an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556885">IQueueCallbackWrite::OnWrite</a> callback function can obtain the buffer access method of an I/O request. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.9

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>
</dt>
<dt>
<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE (UMDF)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest2::GetEffectiveIoType method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

