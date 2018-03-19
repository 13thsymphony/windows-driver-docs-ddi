---
UID: NF:prcomoem.IPrintOemUI.FontInstallerDlgProc
title: IPrintOemUI::FontInstallerDlgProc method
author: windows-driver-content
description: A user interface plug-in's IPrintOemUI::FontInstallerDlgProc method replaces the Unidrv font installer's user interface.
old-location: print\iprintoemui_fontinstallerdlgproc.htm
old-project: print
ms.assetid: 6f63d48d-7c2f-4531-b6db-fd4fdcfbce27
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: FontInstallerDlgProc method [Print Devices], FontInstallerDlgProc method [Print Devices], IPrintOemUI interface, FontInstallerDlgProc,IPrintOemUI.FontInstallerDlgProc, IPrintOemUI, IPrintOemUI interface [Print Devices], FontInstallerDlgProc method, IPrintOemUI::FontInstallerDlgProc, prcomoem/IPrintOemUI::FontInstallerDlgProc, print.iprintoemui_fontinstallerdlgproc, print_unidrv-pscript_ui_f5a028b9-eb7b-4d07-81e8-d7aadc5b8ceb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemUI.FontInstallerDlgProc
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# FontInstallerDlgProc method
A user interface plug-in's <code>IPrintOemUI::FontInstallerDlgProc</code> method replaces the Unidrv font installer's user interface.

## Syntax

````
HRESULT FontInstallerDlgProc(
   HWND   hWnd,
   UINT   usMsg,
   WPARAM wParam,
   LPARAM lParam
);
````

## Parameters

`hWnd`

Window handle.

`usMsg`

Message identifier.

`wParam`

First message parameter.

`lParam`

Second message parameter.


## Return Value

The method must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>

## Remarks

A user interface plug-in can implement the <code>IPrintOemUI::FontInstallerDlgProc</code> method as a means of replacing Unidrv's font installer. For more information, see <a href="https://msdn.microsoft.com/d753368d-b1c8-454e-a02b-131dc778e723">Customized Font Installers for Unidrv</a>.

The <code>IPrintOemUI::FontInstallerDlgProc</code> method is used by Unidrv as a dialog box procedure, and its address is passed to <b>DialogBoxParam</b> (described in the Microsoft Windows SDK documentation) when a user invokes the font installer from Unidrv's user interface.

If the message received for <i>usMsg</i> is WM_INIT or WM_USER+WM_FI_NAME, <i>lParam</i> points to an <a href="..\prntfont\ns-prntfont-_oemfontinstparam.md">OEMFONTINSTPARAM</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554188">IPrintOemUI::UpdateExternalFonts</a>



<a href="..\prcomoem\nn-prcomoem-iprintoemui.md">IPrintOemUI</a>