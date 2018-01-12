---
UID: NF:wudfddi.IWDFIoTarget.GetTargetFile
title: IWDFIoTarget::GetTargetFile method
author: windows-driver-content
description: The GetTargetFile method retrieves the framework file object that is associated with the I/O target object.
old-location: wdf\iwdfiotarget_gettargetfile.htm
old-project: wdf
ms.assetid: d38ede60-9bcf-4c90-8c41-8f1edf1a1d23
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IWDFIoTarget, IWDFIoTarget::GetTargetFile, GetTargetFile
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
req.alt-api: IWDFIoTarget.GetTargetFile
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

# IWDFIoTarget::GetTargetFile method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetTargetFile</b> method retrieves the framework file object that is associated with the I/O target object.



## -syntax

````
void GetTargetFile(
  [out] IWDFFile **ppFileObject
);
````


## -parameters

### -param ppFileObject [out]

Pointer to a buffer that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface for the I/O target's file object.


## -returns
None


## -remarks
If  a framework file object is associated with an I/O target object, the framework includes the file object  with I/O requests that  the driver sends to the I/O target object. 

When a driver formats an I/O request, an I/O target object enables the driver to use either the same file that the request started with or a new file.

The default I/O target has no file object, so a call to <b>GetTargetFile</b> for the default I/O target retrieves <b>NULL</b>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/5633242c-ffab-4af5-9650-7449395deb6b">Using I/O Targets in UMDF</a>.

For a code example of how to use the <b>GetTargetFile</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559236">IWDFIoTarget::FormatRequestForWrite</a>.


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
1.5

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
<a href="..\wudfddi\nn-wudfddi-iwdfiotarget.md">IWDFIoTarget</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoTarget::GetTargetFile method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

