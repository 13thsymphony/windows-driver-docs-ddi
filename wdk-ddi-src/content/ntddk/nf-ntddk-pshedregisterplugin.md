---
UID: NF:ntddk.PshedRegisterPlugin
title: PshedRegisterPlugin function
author: windows-driver-content
description: The PshedRegisterPlugin function registers a PSHED plug-in with the PSHED.
old-location: whea\pshedregisterplugin.htm
old-project: whea
ms.assetid: 8ad93312-932c-417c-8198-9ba515e3d55d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PshedRegisterPlugin, PshedRegisterPlugin function [WHEA Drivers and Applications], ntddk/PshedRegisterPlugin, whea.pshedregisterplugin, whearef_27f04399-dd53-44b3-a31e-350aee53bcb1.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.lib: Pshed.lib
req.dll: Pshed.dll
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Pshed.dll
api_name:
-	PshedRegisterPlugin
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PshedRegisterPlugin function
The <b>PshedRegisterPlugin</b> function registers a PSHED plug-in with the PSHED.

## Syntax

````
NTSTATUS PshedRegisterPlugin(
  _Inout_ PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET Packet
);
````

## Parameters

`Packet`

A pointer to an initialized  <a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure that describes the PSHED plug-in's registration information.


## Return Value

<b>PshedRegisterPlugin</b> returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The PSHED plug-in was successfully registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The data in the supplied registration packet is invalid.

</td>
</tr>
</table>

## Remarks

A PSHED plug-in calls the <b>PshedRegisterPlugin</b> function to register itself with the PSHED. A PSHED plug-in typically calls this function from within either its <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> function or its <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | Pshed.lib |
| **DLL** | Pshed.dll |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a>



<a href="..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>