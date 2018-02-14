---
UID: NF:poscx.PosCxMarkPosApp
title: PosCxMarkPosApp function
author: windows-driver-content
description: PosCxMarkPosApp marks the open instance as associated or not associated with a point-of-service application.
old-location: pos\poscxmarkposapp.htm
old-project: pos
ms.assetid: 6BFFD014-E9DC-495C-9810-0D23BD93C41A
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PosCxMarkPosApp function, poscx/PosCxMarkPosApp, PosCxMarkPosApp, pos.poscxmarkposapp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	poscx.h
apiname:
-	PosCxMarkPosApp
product: Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---


# PosCxMarkPosApp function
PosCxMarkPosApp marks the open instance as associated or not associated with a point-of-service application.

This optional method provides value if the driver implements multiple device interfaces. It helps to  identify which interface is currently in use.

## Syntax

````
NTSTATUS PosCxMarkPosApp(
  _In_ WDFDEVICE     device,
  _In_ WDFFILEOBJECT fileObject,
  _In_ BOOLEAN       isPosApp
);
````

## Parameters

`device`

A handle to a framework device object that represents the device.

`fileObject`

A handle to a framework file object that identifies the caller, usually acquired with <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetfileobject.md">WdfRequestGetFileObject</a>.

`isPosApp`

Specifies if the open instance is associated with a point-of-service application. Set to TRUE if it is associated with a point-of-service application. Otherwise, set to FALSE.


## Return Value

Possible return values are:

<table>
<tr>
<td><b>STATUS_SUCCESS</b></td>
<td>Completed successfully.</td>
</tr>
<tr>
<td><b>INVALID_PARAMETER</b></td>
<td>The specified <i>fileObject</i> is invalid.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | poscx.h (include Poscx.h) |
| **Library** | NtosKrnl.exe |