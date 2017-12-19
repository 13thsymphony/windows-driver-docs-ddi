---
UID: NS.COMPSTUI._PSPINFO
title: _PSPINFO
author: windows-driver-content
description: The PSPINFO structure is used as an input parameter to a property sheet page's dialog box procedure, when the Windows message is WM_INITDIALOG. The dialog box procedure's address is specified in a DLGPAGE structure.
old-location: print\pspinfo.htm
old-project: print
ms.assetid: 80a15ee4-e160-49fc-9c61-a14b14d19751
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _PSPINFO, *PPSPINFO, PPSPINFO, PSPINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: compstui.h
req.include-header: Compstui.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PSPINFO
req.alt-loc: compstui.h
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
---

# _PSPINFO structure



## -description
The PSPINFO structure is used as an input parameter to a property sheet page's dialog box procedure, when the Windows message is WM_INITDIALOG. The dialog box procedure's address is specified in a <a href="print.dlgpage">DLGPAGE</a> structure.



## -syntax

````
typedef struct _PSPINFO {
  WORD            cbSize;
  WORD            wReserved;
  HANDLE          hComPropSheet;
  HANDLE          hCPSUIPage;
  PFNCOMPROPSHEET pfnComPropSheet;
} PSPINFO, *PPSPINFO;
````


## -struct-fields

### -field cbSize

CPSUI-supplied size, in bytes, of the PSPINFO structure.


### -field wReserved

Reserved.


### -field hComPropSheet

CPSUI-supplied handle to the parent of the page whose handle is contained in <b>hCPSUIPage</b>.


### -field hCPSUIPage

CPSUI-supplied handle to the property sheet page.


### -field pfnComPropSheet

CPSUI-supplied pointer to its <a href="print.compropsheet">ComPropSheet</a> function.


## -remarks
Before CPSUI calls <b>CreatePropertySheetPage</b> to create a property sheet page, it expands the size of the standard PROPSHEETPAGE structure in order to append a PSPINFO structure. When the operating system calls a dialog box procedure (pointed to by a <a href="print.dlgpage">DLGPAGE</a> structure) and specifies a WM_INITDIALOG message, the function's <b>lParam</b> member points to the expanded PROPSHEETPAGE structure containing the PSPINFO structure.

(The <b>CreatePropertySheetPage</b> function, PROPSHEETPAGE structure, WM_INITDIALOG message, and dialog box procedures are all described in the Microsoft Windows SDK documentation.)

To obtain the PSPINFO structure's address, use the PPSPINFO_FROM_WM_INITDIALOG_LPARAM macro (defined in compstui.h) as follows:

The PSPINFO structure pointer can be saved for later use, but the structure's contents must not be modified.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Compstui.h (include Compstui.h)</dt>
</dl>
</td>
</tr>
</table>