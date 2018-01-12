---
UID: NF:printerextension.IPrinterExtensionEvent.OnDriverEvent
title: IPrinterExtensionEvent::OnDriverEvent method
author: windows-driver-content
description: Called when a driver event occurs.
old-location: print\iprinterextensionevent_ondriverevent.htm
old-project: print
ms.assetid: F00FD4FB-08D5-42D4-8CC2-85EE02D95E4B
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrinterExtensionEvent, IPrinterExtensionEvent::OnDriverEvent, OnDriverEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrinterExtensionEvent.OnDriverEvent
req.alt-loc: printerextension.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionEvent::OnDriverEvent method



## -description
Called when a driver event occurs.



## -syntax

````
HRESULT OnDriverEvent(
  [in] IPrinterExtensionEventArgs *pEventArgs
);
````


## -parameters

### -param pEventArgs [in]

The event arguments.


## -returns
This method returns an <b>HRESULT</b> value.


## -remarks


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
<dt>Printerextension.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/A0F4DB51-D68E-4516-833A-7E984247796B">IPrinterExtensionEvent</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterextensioneventargs.md">IPrinterExtensionEventArgs</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionEvent::OnDriverEvent method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

