---
UID: NF.winspool.FindFirstPrinterChangeNotification
title: FindFirstPrinterChangeNotification function
author: windows-driver-content
description: Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated.
old-location: print\findfirstprinterchangenotification.htm
old-project: print
ms.assetid: f6d2034a-0906-42ea-a4bd-9cdb1b36c5cf
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: FindFirstPrinterChangeNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winspool.h
req.include-header: Winspool.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FindFirstPrinterChangeNotification
req.alt-loc: WinSpool.drv
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WinSpool.lib
req.dll: WinSpool.drv
req.irql: 
req.product: Windows 10 or later.
---

# FindFirstPrinterChangeNotification function



## -description

## -syntax

````
BOOL FindFirstPrinterChangeNotification(
   HANDLE hPrinter,
   DWORD  fdwFlags,
   DWORD  fdwOptions,
   HANDLE hNotify,
   PDWORD pfdwStatus,
   PVOID  pPrinterNotifyOptions,
   PVOID  pPrinterNotifyInit
);
````


## -parameters

### -param hPrinter 

Caller-supplied printer handle, identifying the printer for which event notification is being requested. This handle must have been previously obtained from OpenPrinter (described in the Microsoft Windows SDK documentation).

### -param fdwFlags 

One or more caller-supplied PRINTER_CHANGE-prefixed flags. For more information, see the description of <b>FindFirstPrinterChangeNotification</b> in the Windows SDK documentation.

### -param fdwOptions 

Not used.

### -param hNotify 

Caller-supplied notification handle. This handle must be saved and used as input to <a href="print.replyprinterchangenotification">ReplyPrinterChangeNotification</a> and <a href="print.partialreplyprinterchangenotification">PartialReplyPrinterChangeNotification</a>.

### -param pfdwStatus 

Caller-supplied pointer to a location to receive provider-specified flags. The following flags are defined.


### -param PRINTER_NOTIFY_STATUS_ENDPOINT 

If set, the print provider supplies print change notifications, by either the polling or the change notification method. (The notification method is identified by the PRINTER_NOTIFY_STATUS_POLL flag.)
</dd>
</dl>


### -param PRINTER_NOTIFY_STATUS_POLL 

If set, the print application must poll to detect printer changes.
If clear, the print provider notifies the spooler of changes by calling <a href="print.refreshprinterchangenotification">RefreshPrinterChangeNotification</a>.
(See the following Remarks section.)
</dd>
</dl>


### -param PRINTER_NOTIFY_STATUS_INFO 

Not used.
</dd>
</dl>

### -param pPrinterNotifyOptions 

Caller-supplied pointer to a PRINTER_NOTIFY_OPTIONS structure (described in the Windows SDK documentation).

### -param pPrinterNotifyInit 

Not used.

## -returns
If the operation succeeds, the function should return <b>TRUE</b>. Otherwise the function should return <b>FALSE</b>.

## -remarks
When the spooler calls a print provider's <b>FindFirstPrinterChangeNotification</b> function, <i>fdwFlags</i> identifies the printer events for which notification is being requested. Additionally, <i>pPrinterNotifyOptions</i> identifies the types of information that the print provider should send to the spooler when one of the specified events occurs.

For a list of the types of notifications an application can request, and for a list of the types of information that can be used to describe an event, see the Windows SDK documentation's description of <b>FindFirstPrinterChangeNotification</b>. Types of events for which an application might request notification include adding or deleting a print job or form. Types of information an application might request include job or form parameters.

If the print provider does not request polling (that is, it does not set PRINTER_NOTIFY_STATUS_POLL in <i>pfdwStatus</i>), it must notify the spooler when events identified by <i>pfwFlags</i> occur. The print provider must supply the types of information identified by <i>pPrinterNotifyOptions</i>, by calling <a href="print.partialreplyprinterchangenotification">PartialReplyPrinterChangeNotification</a> or <a href="print.replyprinterchangenotification">ReplyPrinterChangeNotification</a>.

If the provider does request polling (that is, it sets PRINTER_NOTIFY_STATUS_POLL), it should not call <b>ReplyPrinterChangeNotification</b>. Instead, the spooler signals the application at regular intervals.

Both polled and nonpolled print provider must return the current state of all requested information types whenever its <a href="print.refreshprinterchangenotification">RefreshPrinterChangeNotification</a> function is called.

For additional information, see <a href="https://msdn.microsoft.com/e75c6f89-9cef-4900-af89-edf1f7f786c7">Supporting Printer Change Notifications</a>.

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
Header
</th>
<td width="70%">
<dl>
<dt>Winspool.h (include Winspool.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>WinSpool.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>WinSpool.drv</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.partialreplyprinterchangenotification">PartialReplyPrinterChangeNotification</a>
</dt>
<dt>
<a href="print.replyprinterchangenotification">ReplyPrinterChangeNotification</a>
</dt>
<dt>
<a href="print.refreshprinterchangenotification">RefreshPrinterChangeNotification</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20FindFirstPrinterChangeNotification function%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
