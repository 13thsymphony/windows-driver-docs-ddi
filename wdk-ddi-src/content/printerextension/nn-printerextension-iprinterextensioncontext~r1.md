---
UID: NN.printerextension.IPrinterExtensionContext~r1
title: IPrinterExtensionContext
author: windows-driver-content
description: Represents the context for the activation of a UWP device app for printers.
old-location: print\iprinterextensioncontext_interface.htm
ms.assetid: DD0B5E6F-8E16-48E1-967B-D188535E1320
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: interface
ms.prod: windows-hardware
ms.technology: print
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrinterExtensionContext
req.alt-loc: Printerextension.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
ms.keywords: IPrintSchemaTicket2, GetParameterInitializer, IPrintSchemaTicket2::GetParameterInitializer
req.iface: IPrintSchemaTicket2
req.product: Windows 10 or later.
---

# IPrinterExtensionContext interface



## -description
<p>Represents the context for the activation of a UWP device app for printers.</p>


## -inheritance
<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterExtensionContext</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IDispatch</b></a> interface. <b>IPrinterExtensionContext</b> also has these types of members:</p>

<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterExtensionContext</b> interface has these properties.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973203">DriverProperties</a>
</p>

<p>Read-only</p>

<p>Gets the driver property bag.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973204">PrinterQueue</a>
</p>

<p>Read-only</p>

<p>Gets the queue for the printer.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973205">PrintSchemaTicket</a>
</p>

<p>Read-only</p>

<p>Gets the print ticket that is appropriate for the queue and the activation.</p>

<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973206">UserProperties</a>
</p>

<p>Read-only</p>

<p>Gets the user property bag for this app.</p>

<p> </p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Printerextension.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh846191">IPrinterExtensionContextCollection</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/F2279727-168D-451B-8EDB-8A4A36ACA08F">IPrinterExtensionContextCollection::Count</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/5E3DC6C7-E370-4120-81B7-2093812AD009">IPrinterExtensionContextCollection::GetAt</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/947063C6-563A-4BB7-918E-479941B4583F">IPrinterExtensionEvent::OnPrinterQueuesEnumerated</a>
</dt>
<dt>
<a href="NULL">V4 Printer Driver Property Bags</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionContext interface%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
