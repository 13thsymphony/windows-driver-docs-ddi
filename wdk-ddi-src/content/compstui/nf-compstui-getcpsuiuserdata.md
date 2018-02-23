---
UID: NF:compstui.GetCPSUIUserData
title: GetCPSUIUserData function
author: windows-driver-content
description: CPSUI's GetCPSUIUserData function retrieves data that was previously stored using the SetCPSUIUserData function.
old-location: print\getcpsuiuserdata.htm
old-project: print
ms.assetid: 2a0a74cd-2dcf-4485-8941-7f205dcecede
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: cpsuifnc_78057e6d-1a47-4b92-9d43-881ab0935169.xml, GetCPSUIUserData function [Print Devices], compstui/GetCPSUIUserData, print.getcpsuiuserdata, GetCPSUIUserData
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
req.lib: Compstui.lib
req.dll: Compstui.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Compstui.dll
apiname:
-	GetCPSUIUserData
product: Windows
targetos: Windows
req.typenames: "*PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX"
---


# GetCPSUIUserData function
CPSUI's <b>GetCPSUIUserData</b> function retrieves data that was previously stored using the <a href="..\compstui\nf-compstui-setcpsuiuserdata.md">SetCPSUIUserData</a> function.

## Syntax

````
ULONG_PTR GetCPSUIUserData(
   HWND hDlg
);
````

## Parameters

`hDlg`

Caller-supplied handle to a property sheet dialog box. For more information, see the following Remarks section.


## Return Value

If the operation succeeds, the function returns the value that was previously supplied to <a href="..\compstui\nf-compstui-setcpsuiuserdata.md">SetCPSUIUserData</a>; otherwise the function returns zero.

## Remarks

The <b>GetCPSUIUserData</b> function should only be called from within a dialog box procedure that has been associated with a dialog box by using a <a href="..\compstui\ns-compstui-_dlgpage.md">DLGPAGE</a> or an <a href="..\compstui\ns-compstui-_extpush.md">EXTPUSH</a> structure.

The handle specified for <i>hDlg</i> must be the handle received as input to the dialog box procedure. (Dialog box procedures are described in the Microsoft Windows SDK documentation.)

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | compstui.h (include Compstui.h) |
| **Library** | Compstui.lib |
| **DLL** | Compstui.dll |