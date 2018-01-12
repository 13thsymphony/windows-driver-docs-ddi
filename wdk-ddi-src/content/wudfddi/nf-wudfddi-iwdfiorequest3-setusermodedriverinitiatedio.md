---
UID: NF:wudfddi.IWDFIoRequest3.SetUserModeDriverInitiatedIo
title: IWDFIoRequest3::SetUserModeDriverInitiatedIo method
author: windows-driver-content
description: The SetUserModeDriverInitiatedIo method indicates to kernel-mode drivers that sit below the UMDF driver in the same device stack that a particular request should be treated as though it came from a UMDF driver.
old-location: wdf\iwdfiorequest3_setusermodedriverinitiatedio.htm
old-project: wdf
ms.assetid: F494ED4C-DA2F-4630-B0CA-8B3BE7D26A80
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IWDFIoRequest3, IWDFIoRequest3::SetUserModeDriverInitiatedIo, SetUserModeDriverInitiatedIo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: IWDFIoRequest3.SetUserModeDriverInitiatedIo
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

# IWDFIoRequest3::SetUserModeDriverInitiatedIo method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetUserModeDriverInitiatedIo</b> method 
   
  indicates to kernel-mode drivers that sit below the UMDF driver in the same device stack that a particular request should be treated as though it came from a UMDF driver.



## -syntax

````
void SetUserModeDriverInitiatedIo(
  [in] BOOL IsUserModeDriverInitiated
);
````


## -parameters

### -param IsUserModeDriverInitiated [in]

A Boolean value that, if <b>TRUE</b>, indicates that the request should be treated as though it was initiated by a UMDF driver. If <b>FALSE</b>, this parameter indicates that the request should be treated as though it came from an application.


## -returns
This method does not return a value.


## -remarks
If a UMDF driver calls this method with the <i>IsUserModeDriverInitiated</i> parameter set to <b>TRUE</b>, the framework sets the IRP_UM_DRIVER_INITIATED_IO flag in the <b>Flags</b> member of the WDM <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure before forwarding the request to kernel-mode drivers.

A kernel-mode driver that resides below the UMDF driver in the same device stack can check for this flag to determine if the request should be treated as though initiated by a UMDF driver.

This flag is not applicable to kernel-mode drivers that might receive a request from a UMDF driver via a file-handle I/O target or a Win32 I/O target.

A UMDF driver might set the <i>IsUserModeDriverInitiated</i> parameter to <b>TRUE</b> for a request that came from an application if the driver has validated the request.

Requests that the driver created on its own are already marked as having originated from a UMDF driver.

The UMDF 2 equivalent of this method is <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetusermodedriverinitiatedio.md">WdfRequestSetUserModeDriverInitiatedIo</a>.


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
1.11

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
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest3.md">IWDFIoRequest3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451341">GetUserModeDriverInitiatedIo</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetusermodedriverinitiatedio.md">WdfRequestSetUserModeDriverInitiatedIo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest3::SetUserModeDriverInitiatedIo method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

