---
UID: NF:compstui.CommonPropertySheetUIW
title: CommonPropertySheetUIW function
author: windows-driver-content
description: CPSUI's CommonPropertySheetUI function displays property sheet pages and allows user modifications to displayed values.
old-location: print\commonpropertysheetui.htm
old-project: print
ms.assetid: 63d88589-455a-4923-bb3a-61d977732603
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CommonPropertySheetUI, CommonPropertySheetUI function [Print Devices], CommonPropertySheetUIA, CommonPropertySheetUIW, compstui/CommonPropertySheetUI, cpsuifnc_547a4235-9e08-43fc-acae-b30091032ab3.xml, print.commonpropertysheetui
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: compstui.h
req.include-header: Compstui.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	compstui.h
api_name:
-	CommonPropertySheetUI
product: Windows
targetos: Windows
req.typenames: POWERSOURCEUPDATEEX, *PPOWERSOURCEUPDATEEX
---


# CommonPropertySheetUIW function
CPSUI's <b>CommonPropertySheetUI</b> function displays property sheet pages and allows user modifications to displayed values.

## Syntax

````
LONG CommonPropertySheetUI(
   HWND           hWndOwner,
   PFNPROPSHEETUI pfnPropSheetUI,
   LPARAM         lParam,
   LPDWORD        pResult
);
````

## Parameters

`hWndOwner`

Caller-supplied window handle identifying the window into which new property sheet pages are to be placed.

`pfnPropSheetUI`

Caller-supplied pointer to a <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>-typed callback function.

`lParam`

Caller-supplied value that is used as an input argument to the <i>pfnPropSheetUI</i> function. This value can be a pointer.

`pResult`

Caller-supplied pointer to a DWORD that receives the <i>pfnPropSheetUI</i> function's final return status. If <b>NULL</b>, the final return status is not returned. For more information, see the following Remarks section.


## Return Value

The <b>CommonPropertySheetUI</b> function returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>CPSUI_CANCEL</b></dt>
</dl>
</td>
<td width="60%">
The <i>pfnPropSheetUI</i> function returned a negative value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>CPSUI_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>CPSUI_REBOOTSYSTEM</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded, and a dialog box procedure sent the PSM_REBOOTSYSTEM message (defined in the Microsoft Windows SDK documentation).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>CPSUI_RESTARTWINDOWS</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded, and a dialog box procedure sent the PSM_RESTARTWINDOWS message (defined in the Windows SDK documentation).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERR_CPSUI-prefixed error code</b></dt>
</dl>
</td>
<td width="60%">
A failure occurred. The ERR_CPSUI-prefixed error codes are defined in compstui.h.

</td>
</tr>
</table>

## Remarks

The <b>CommonPropertySheetUI</b> function is CPSUI's entry point for applications. A CPSUI application (such as the Microsoft NT-based operating system print spooler) can call the function to add one or more property sheet pages to a predefined parent window. CPSUI displays the pages, allows the user to modify them, and notifies the application of user activity through callback functions.

The NT-based operating system print spooler calls the <b>CommonPropertySheetUI</b> function when a Win32 application calls the spooler's DocumentProperties or PrinterProperties functions, which are described in the Windows SDK documentation.

The callback function specified by the <i>pfnPropSheetUI</i> parameter is responsible for describing the property sheet pages to be added. For more information, see the description of the <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> function type.

The sequence of operation is as follows:

<ol>
<li>
The <b>CommonPropertySheetUI</b> function calls the <i>pfnPropSheetUI</i> callback so the callback can describe the pages to be added by calling CPSUI's <a href="..\compstui\nc-compstui-pfncompropsheet.md">ComPropSheet</a> function.

</li>
<li>
If the <i>pfnPropSheetUI</i> callback succeeds, the <b>CommonPropertySheetUI</b> function displays the new property sheet pages and allows the user to modify page values.

</li>
<li>
If the user modifies page values, a <a href="https://msdn.microsoft.com/891f62ec-d009-42c8-8143-73bfe737a946">page event callback</a> notifies the application of the changes.

</li>
<li>
When the user chooses the <b>OK</b> or <b>Cancel</b> button, the <b>CommonPropertySheetUI</b> function destroys the displayed pages and returns.

</li>
</ol>
For more information about the sequence of operation, see <a href="https://msdn.microsoft.com/898a855d-6a9a-4f98-9ee4-bad439427326">Using CPSUI with Printer Drivers</a>, in the section entitled <a href="https://msdn.microsoft.com/7af3435a-19e0-40a1-9f94-319d9d323856">CPSUI</a>.

The <b>CommonPropertySheetUI</b> function actually calls the <i>pfnPropSheetUI</i> callback several times, specifying different <b>Reason</b> member values in the callback's <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure. Each time the callback returns, it places a result status in the PROPSHEETUI_INFO structure's <b>Result</b> member. When the <b>CommonPropertySheetUI</b> function returns, it copies the final contents of <b>Result</b> into the location pointed to by <i>pResult</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | compstui.h (include Compstui.h) |
| **Library** | NtosKrnl.exe |