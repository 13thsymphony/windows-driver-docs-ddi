---
UID: NF.winsplp.PartialReplyPrinterChangeNotification
title: PartialReplyPrinterChangeNotification
author: windows-driver-content
description: The print spooler's PartialReplyPrinterChangeNotification function allows a print provider to update the spooler's database of printer changes associated with a notification handle.
old-location: print\partialreplyprinterchangenotification.htm
old-project: print
ms.assetid: a884920c-1824-418f-90c8-0edf1381678b
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: PartialReplyPrinterChangeNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PartialReplyPrinterChangeNotification
req.alt-loc: Spoolss.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# PartialReplyPrinterChangeNotification function



## -description
<p>The print spooler's <code>PartialReplyPrinterChangeNotification</code> function allows a print provider to update the spooler's database of printer changes associated with a notification handle.</p>


## -syntax

````
BOOL PartialReplyPrinterChangeNotification(
  _In_     HANDLE                    hNotify,
  _In_opt_ PPRINTER_NOTIFY_INFO_DATA pInfoDataSrc
);
````


## -parameters
<dl>

### -param <i>hNotify</i> [in]

<dd>
<p>Caller-supplied handle. This handle must have been previously received as the <i>hNotify</i> input to the print provider's <a href="..\winspool\nf-winspool-findfirstprinterchangenotification.md">FindFirstPrinterChangeNotification</a> function.</p>
</dd>

### -param <i>pInfoDataSrc</i> [in, optional]

<dd>
<p>Caller-supplied pointer to a PRINTER_NOTIFY_INFO_DATA structure (described in the Microsoft Windows SDK documentation). Can be <b>NULL</b>. For more information, see the following Remarks section.</p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>. The caller can obtain an error code by calling <b>GetLastError</b>.</p>

## -remarks
<p>For the specified notification handle, the spooler's <code>PartialReplyPrinterChangeNotification</code> function adds the contents of the specified PRINTER_NOTIFY_INFO_DATA structure to the array within the spooler's stored PRINTER_NOTIFY_INFO structure. (These structures are described in the Windows SDK documentation.)</p>

<p>Calling <code>PartialReplyPrinterChangeNotification</code> does not cause the spooler to notify the application that changes have occurred. If the print provider's <a href="..\winspool\nf-winspool-findfirstprinterchangenotification.md">FindFirstPrinterChangeNotification</a> function did not set the PRINTER_NOTIFY_STATUS_POLL flag, the provider must call <a href="..\winsplp\nf-winsplp-replyprinterchangenotification.md">ReplyPrinterChangeNotification</a> to cause the application to be notified.</p>

<p>If <i>pInfoDataSrc</i> is <b>NULL</b>, all stored information associated with the specified handle is deleted from the spooler. The function accomplishes this deletion by freeing all buffers associated with <i>pBuf</i> members of PRINTER_NOTIFY_INFO_DATA structures belonging to the specified handle. The function then sets the PRINTER_NOTIFY_INFO_DISCARDED flag in the stored PRINTER_NOTIFY_INFO structure.</p>

<p>For additional information, see <a href="NULL">Supporting Printer Change Notifications</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Winsplp.h (include Winsplp.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Spoolss.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Spoolss.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\winspool\nf-winspool-findfirstprinterchangenotification.md">FindFirstPrinterChangeNotification</a>
</dt>
<dt>
<a href="..\winsplp\nf-winsplp-replyprinterchangenotification.md">ReplyPrinterChangeNotification</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PartialReplyPrinterChangeNotification function%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
