---
UID: NS.PRINTOEM._OEMUIPSPARAM
title: _OEMUIPSPARAM
author: windows-driver-content
description: The OEMUIPSPARAM structure is passed to a user interface plug-in's IPrintOemUI::DevicePropertySheets and IPrintOemUI::DocumentPropertySheets methods.
old-location: print\oemuipsparam.htm
old-project: print
ms.assetid: e7708b33-b032-41b9-84f9-6c5b38044f9c
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: _OEMUIPSPARAM, *POEMUIPSPARAM, OEMUIPSPARAM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OEMUIPSPARAM
req.alt-loc: printoem.h
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
req.product: Windows 10 or later.
---

# _OEMUIPSPARAM structure



## -description
The OEMUIPSPARAM structure is passed to a user interface plug-in's <a href="print.iprintoemui_devicepropertysheets">IPrintOemUI::DevicePropertySheets</a> and <a href="print.iprintoemui_documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a> methods.



## -syntax

````
typedef struct _OEMUIPSPARAM {
  DWORD     cbSize;
  POEMUIOBJ poemuiobj;
  HANDLE    hPrinter;
  PWSTR     pPrinterName;
  HANDLE    hModule;
  HANDLE    hOEMHeap;
  PDEVMODE  pPublicDM;
  PVOID     pOEMDM;
  PVOID     pOEMUserData;
  DWORD     dwFlags;
  PVOID     pOemEntry;
} OEMUIPSPARAM, *POEMUIPSPARAM;
````


## -struct-fields

### -field cbSize

Size of the OEMUIPSPARAM structure. Supplied by the Unidrv or Pscript5 driver.


### -field poemuiobj

Not used.


### -field hPrinter

Handle to the printer. Supplied by the Unidrv or Pscript5 driver.


### -field pPrinterName

String containing the printer name. Supplied by the Unidrv or Pscript5 driver.


### -field hModule

Handle to the user interface plug-in. Supplied by the Unidrv or Pscript5 driver.


### -field hOEMHeap

Handle to a heap from which space can be allocated by calling the Microsoft Windows SDK <b>HeapAlloc</b> function. Supplied by the Unidrv or Pscript5 driver.


### -field pPublicDM




### -field For calls to IPrintOemUI::DocumentPropertySheets:

Caller-supplied pointer to the printer's public DEVMODEW structure.


### -field For calls to IPrintOemUI::DevicePropertySheets:

Not used.

</dd>
</dl>

### -field pOEMDM




### -field For calls to IPrintOemUI::DocumentPropertySheets:

Caller-supplied pointer to the user interface plug-in's private DEVMODEW members.


### -field For calls to IPrintOemUI::DevicePropertySheets:

Not used.

</dd>
</dl>

### -field pOEMUserData

Pointer, supplied by user interface plug-in, to a location containing private information. This pointer is returned to the plug-in's <a href="..\compstui\nc-compstui-_cpsuicallback.md">_CPSUICALLBACK</a>-typed callback function when a property sheet item has changed.


### -field dwFlags




### -field For calls to IPrintOemUI::DocumentPropertySheets:

Contains the contents of the <b>fMode</b> member of the DOCUMENTPROPERTYHEADER structure received by the printer driver's <a href="print.drvdocumentpropertysheets">DrvDocumentPropertySheets</a> function.


### -field For calls to IPrintOemUI::DevicePropertySheets:

Contains the contents of the <b>Flags</b> member of the DEVICEPROPERTYHEADER structure received by the printer driver's <a href="print.drvdevicepropertysheets">DrvDevicePropertySheets</a> function.

</dd>
</dl>

### -field pOemEntry

Reserved for system use.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Printoem.h (include Printoem.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.iprintoemui_devicepropertysheets">IPrintOemUI::DevicePropertySheets</a>
</dt>
<dt>
<a href="print.iprintoemui_documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a>
</dt>
<dt>
<a href="..\compstui\nc-compstui-_cpsuicallback.md">_CPSUICALLBACK</a>
</dt>
<dt>
<a href="print.drvdocumentpropertysheets">DrvDocumentPropertySheets</a>
</dt>
<dt>
<a href="print.drvdevicepropertysheets">DrvDevicePropertySheets</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20OEMUIPSPARAM structure%20 RELEASE:%20(12/9/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

