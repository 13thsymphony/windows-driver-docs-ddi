---
UID: NF.compstui.SetCPSUIUserData
title: SetCPSUIUserData function
author: windows-driver-content
description: CPSUI's SetCPSUIUserData function allows CPSUI applications (including printer interface DLLs) to associate nondisplayed data with a property sheet dialog box.
old-location: print\setcpsuiuserdata.htm
old-project: print
ms.assetid: 35119100-adf9-4376-bb1a-7317733fbcc5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SetCPSUIUserData
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
req.alt-api: SetCPSUIUserData
req.alt-loc: Compstui.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Compstui.lib
req.dll: Compstui.dll
req.irql: 
---

# SetCPSUIUserData function



## -description
CPSUI's <code>SetCPSUIUserData</code> function allows CPSUI applications (including printer interface DLLs) to associate nondisplayed data with a property sheet dialog box.



## -syntax

````
BOOL SetCPSUIUserData(
   HWND      hDlg,
   ULONG_PTR CPSUIUserData
);
````


## -parameters

### -param hDlg 

Caller-supplied handle to a property sheet dialog box. For more information, see the following Remarks section.


### -param CPSUIUserData 

Caller-supplied value to be stored.


## -returns
The  function returns <b>TRUE</b> if it is successful in associating the nondisplayed data with the property sheet dialog box, and <b>FALSE</b> otherwise.


## -remarks
The <code>SetCPSUIUserData</code> function should be called only from within a dialog box procedure that has been associated with a dialog box by using a <a href="print.dlgpage">DLGPAGE</a> or an <a href="print.extpush">EXTPUSH</a> structure.

A value that is stored by calling <code>SetCPSUIUserData</code> can be later retrieved by calling <a href="print.getcpsuiuserdata">GetCPSUIUserData</a>.

The handle specified for <i>hDlg</i> must be the handle received as input to the dialog box procedure. (Dialog box procedures are described in the Microsoft Windows SDK documentation.)


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
<dt>Compstui.h (include Compstui.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Compstui.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Compstui.dll</dt>
</dl>
</td>
</tr>
</table>