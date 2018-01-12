---
UID: NF:ucxcontroller.UcxControllerSetIdStrings
title: UcxControllerSetIdStrings function
author: windows-driver-content
description: Updates the identifier strings of a controller after the controller has been initialized.
old-location: buses\ucxcontrollersetidstrings.htm
old-project: usbref
ms.assetid: FC0F6C02-C53A-4F7E-B718-70788FA807F3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UcxControllerSetIdStrings
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: UcxControllerSetIdStrings
req.alt-loc: Ucxstubs.lib,Ucxstubs.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ucxstubs.lib
req.dll: 
req.irql: 
req.typenames: UCX_CONTROLLER_STATE
req.product: Windows 10 or later.
---

# UcxControllerSetIdStrings function



## -description
Updates the identifier strings
    of a controller after the controller has been initialized.



## -syntax

````
NTSTATUS UcxControllerSetIdStrings(
  _In_ UCXCONTROLLER   UcxController,
  _In_ PUNICODE_STRING ManufacturerNameString,
  _In_ PUNICODE_STRING ModelNameString,
  _In_ PUNICODE_STRING ModelNumberString
);
````


## -parameters

### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param ManufacturerNameString [in]

A string that contains the name of controller manufacturer.


### -param ModelNameString [in]

A string that contains the name of device model.


### -param ModelNumberString [in]

A string that contains the revision number of the device model.


## -returns
The function returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1709

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucxcontroller.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ucxstubs.lib</dt>
</dl>
</td>
</tr>
</table>