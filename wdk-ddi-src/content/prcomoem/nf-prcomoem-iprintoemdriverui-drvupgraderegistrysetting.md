---
UID: NF:prcomoem.IPrintOemDriverUI.DrvUpgradeRegistrySetting
title: IPrintOemDriverUI::DrvUpgradeRegistrySetting method
author: windows-driver-content
description: The IPrintOemDriverUI::DrvUpdateRegistrySetting method is provided by the Unidrv and Pscript5 minidrivers so that user interface plug-ins can update device settings stored in the registry.
old-location: print\iprintoemdriverui_drvupgraderegistrysetting.htm
old-project: print
ms.assetid: 9249dd75-7d90-414a-b6b5-4be0fc4f3170
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DrvUpgradeRegistrySetting method [Print Devices], DrvUpgradeRegistrySetting method [Print Devices], IPrintOemDriverUI interface, DrvUpgradeRegistrySetting,IPrintOemDriverUI.DrvUpgradeRegistrySetting, IPrintOemDriverUI, IPrintOemDriverUI interface [Print Devices], DrvUpgradeRegistrySetting method, IPrintOemDriverUI::DrvUpgradeRegistrySetting, prcomoem/IPrintOemDriverUI::DrvUpgradeRegistrySetting, print.iprintoemdriverui_drvupgraderegistrysetting, print_unidrv-pscript_ui_f87ff21a-a7c2-49b5-857a-2ef201c2f13f.xml
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
-	IPrintOemDriverUI.DrvUpgradeRegistrySetting
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# IPrintOemDriverUI::DrvUpgradeRegistrySetting method
The <code>IPrintOemDriverUI::DrvUpdateRegistrySetting</code> method is provided by the Unidrv and Pscript5 minidrivers so that user interface plug-ins can update device settings stored in the registry.

## Syntax

```
HRESULT DrvUpgradeRegistrySetting(
  HANDLE hPrinter,
  PCSTR  pFeature,
  PCSTR  pOption
);
```

## Parameters

`hPrinter`

Caller-supplied printer handle.

`pFeature`

Caller-supplied pointer to a string identifying a printer feature name contained in the printer's <a href="https://msdn.microsoft.com/f67c673d-c6f0-49f0-850a-d8b00e99ddd4">GPD</a> or <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PPD</a> file.

`pOption`

Caller-supplied pointer to a string identifying an option name, associated with the specified feature, contained in the printer's GPD or PPD file.


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

The <code>IPrintOemDriverUI::DrvUpdateRegistrySetting</code> method is meant to be called from a user interface plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554189">IPrintOemUI::UpgradePrinter</a> method, when it is necessary to update registry settings that were stored in private registry keys for an earlier version of the driver, but are now contained in a GPD or PPD file.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |