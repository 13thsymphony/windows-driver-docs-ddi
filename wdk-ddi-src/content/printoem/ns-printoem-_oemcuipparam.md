---
UID: NS.PRINTOEM._OEMCUIPPARAM
title: _OEMCUIPPARAM
author: windows-driver-content
description: The OEMCUIPPARAM structure is used as an input parameter to a user interface plug-in's IPrintOemUI::CommonUIProp method.
old-location: print\oemcuipparam.htm
old-project: print
ms.assetid: 178b635c-0916-44f5-87a3-a2766601dcab
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _OEMCUIPPARAM, OEMCUIPPARAM, *POEMCUIPPARAM
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
req.alt-api: OEMCUIPPARAM
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

# _OEMCUIPPARAM structure



## -description
The OEMCUIPPARAM structure is used as an input parameter to a user interface plug-in's <a href="print.iprintoemui_commonuiprop">IPrintOemUI::CommonUIProp</a> method.



## -syntax

````
typedef struct _OEMCUIPPARAM {
  DWORD           cbSize;
  POEMUIOBJ       poemuiobj;
  HANDLE          hPrinter;
  PWSTR           pPrinterName;
  HANDLE          hModule;
  HANDLE          hOEMHeap;
  PDEVMODE        pPublicDM;
  PVOID           pOEMDM;
  DWORD           dwFlags;
  POPTITEM        pDrvOptItems;
  DWORD           cDrvOptItems;
  POPTITEM        pOEMOptItems;
  DWORD           cOEMOptItems;
  PVOID           pOEMUserData;
  OEMCUIPCALLBACK OEMCUIPCallback;
} OEMCUIPPARAM;
````


## -struct-fields

### -field cbSize

Size of the OEMCUIPPARAM structure. Supplied by the Unidrv or Pscript5 driver.


### -field poemuiobj

Pointer to an <a href="print.oemuiobj">OEMUIOBJ</a> structure.


### -field hPrinter

Handle to the printer. Supplied by the Unidrv or Pscript5 driver.


### -field pPrinterName

String containing the printer name. Supplied by the Unidrv or Pscript5 driver.


### -field hModule

Handle to the user interface plug-in. Supplied by the Unidrv or Pscript5 driver.


### -field hOEMHeap

Handle to a heap from which space can be allocated by calling the <b>HeapAlloc</b> function (described in the Microsoft Windows SDK documentation). Supplied by the Unidrv or Pscript5 driver.


### -field pPublicDM

Pointer to the printer's public DEVMODEW structure. Valid only if the <a href="print.iprintoemui_commonuiprop">IPrintOemUI::CommonUIProp</a> method's <i>dwMode</i> argument is OEMCUIP_DOCPROP. Supplied by the Unidrv or Pscript5 driver.


### -field pOEMDM

Pointer to the user interface plug-in's private DEVMODEW members. Valid only if the <b>IPrintOemUI::CommonUIProp</b> method's <i>dwMode</i> argument is OEMCUIP_DOCPROP. Supplied by the Unidrv or Pscript5 driver.


### -field dwFlags




### -field For calls to IPrintOemUI::CommonUIProp with its dwMode parameter set to OEMCUIP_DOCPROP:

Contains the contents of the <b>fMode</b> member of the <a href="print.documentpropertyheader">DOCUMENTPROPERTYHEADER</a> structure received by the printer driver's <a href="print.drvdocumentpropertysheets">DrvDocumentPropertySheets</a> function.


### -field For calls to IPrintOemUI::CommonUIProp with its dwMode parameter set to OEMCUIP_PRNPROP:

Contains the contents of the <b>Flags</b> member of the DEVICEPROPERTYHEADER structure received by the printer driver's <a href="print.drvdevicepropertysheets">DrvDevicePropertySheets</a> function.

</dd>
</dl>

### -field pDrvOptItems

Pointer to the printer driver's <a href="print.optitem">OPTITEM</a> array. Not valid the first time <b>IPrintOemUI::CommonUIProp</b> is called. Supplied by the Unidrv or Pscript5 driver.


### -field cDrvOptItems

Count of OPTITEM structures in the array pointed to by <b>pDrvOptItems</b>. Supplied by the Unidrv or Pscript5 driver.


### -field pOEMOptItems

Pointer to an array of OPTITEM structures. Supplied by <b>IPrintOemUI::CommonUIProp</b> caller. The second time the <b>IPrintOemUI::CommonUIProp</b> method is called, it must place OPTITEM structures defined by the user interface plug-in in this array, and it must place the structure count in <b>cOEMOptItems</b>. For each OPTITEM structure placed in the array, you must do the following:

<ul>
<li>
Set the OPTITEM structure's <b>DMPubID</b> member either to one of the predefined values or to a value greater than DMPUB_USER. If you use any predefined values, you must search through the entire OPTITEM array for structures already containing those values, and you must set their OPTIF_HIDE flags.

</li>
<li>
Allocate space for OPTTYPES and OPTPARAMS structures by calling the Windows SDK <b>HeapAlloc</b> function, using the handle contained in the OEMCUIPPARAM structure's <b>hOEMHeap</b> member. The printer driver deallocates this space when it is no longer needed.

</li>
</ul>
Not valid the first time <b>IPrintOemUI::CommonUIProp</b> is called.


### -field cOEMOptItems

Count of OPTITEM structures contained in the array pointed by <b>pOEMOptItems</b>. Supplied by the Unidrv or Pscript5 driver.

The first time the <b>IPrintOemUI::CommonUIProp</b> method is called, the caller-supplied value for <b>cOEMOptItems</b> is zero. The <b>IPrintOemUI::CommonUIProp</b> method must change this value to indicate the number of OPTITEM structures that the method supplies. The second time it is called, <b>IPrintOemUI::CommonUIProp</b> must supply the number of OPTITEM structures actually added to the array pointed to by <b>pOEMOptItems</b>.


### -field pOEMUserData

Used by the <b>IPrintOemUI::CommonUIProp</b> method, the second time it is called, to provide the <b>OEMCUIPCallback</b> function with optional extra input information.


### -field OEMCUIPCallback

Used by the <b>IPrintOemUI::CommonUIProp</b> method, the second time it is called, to return the address of a callback function of type <a href="..\printoem\nc-printoem-oemcuipcallback.md">OEMCUIPCALLBACK</a>.


## -remarks
A user interface plug-in receives this structure's address as an input argument to both its <a href="print.iprintoemui_commonuiprop">IPrintOemUI::CommonUIProp</a> method and its <a href="..\printoem\nc-printoem-oemcuipcallback.md">OEMCUIPCALLBACK</a>-typed callback function.

For additional information about the use of this structure and associated functions, see <a href="https://msdn.microsoft.com/22ac2af6-37d8-4913-95af-9c3dc8576d40">User Interface Plug-Ins</a>.


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