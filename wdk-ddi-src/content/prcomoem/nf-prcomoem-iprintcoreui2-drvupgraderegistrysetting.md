---
UID: NF.prcomoem.IPrintCoreUI2.DrvUpgradeRegistrySetting
title: IPrintCoreUI2::DrvUpgradeRegistrySetting
author: windows-driver-content
description: The IPrintCoreUI2::DrvUpgradeRegistrySetting method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can update device settings stored in the registry.
old-location: print\iprintcoreui2_drvupgraderegistrysetting.htm
old-project: print
ms.assetid: c9fa1506-ffef-44a8-9b25-9033280e0c33
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPrintCoreUI2, DrvUpgradeRegistrySetting, IPrintCoreUI2::DrvUpgradeRegistrySetting
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintCoreUI2.DrvUpgradeRegistrySetting
req.alt-loc: Prcomoem.h
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
req.iface: IPrintCoreUI2
req.product: Windows 10 or later.
---

# IPrintCoreUI2::DrvUpgradeRegistrySetting method



## -description
<p>The <code>IPrintCoreUI2::DrvUpgradeRegistrySetting</code> method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can update device settings stored in the registry.</p>


## -syntax

````
STDMETHOD DrvUpgradeRegistrySetting(
   HANDLE hPrinter ,
   PCSTR  pFeature,
   PCSTR  pOption
);
````


## -parameters
<dl>

### -param hPrinter  

<dd>
<p>Caller-supplied printer handle.</p>
</dd>

### -param pFeature 

<dd>
<p>Caller-supplied pointer to a string identifying a printer feature name contained in the printer's GPD or PPD file.</p>
</dd>

### -param pOption 

<dd>
<p>Caller-supplied pointer to a string identifying an option name, associated with the specified feature, contained in the printer's GPD or PPD file.</p>
</dd>
</dl>

## -returns
<p>The method must return one of the following values.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The operation succeeded.</p><dl>
<dt><b>E_FAIL</b></dt>
</dl><p>The operation failed.</p><dl>
<dt><b>E_NOTIMPL</b></dt>
</dl><p>The method is not implemented.</p>

<p> </p>

## -remarks
<p>This method is inherited from the <a href="https://msdn.microsoft.com/ed11789f-750d-4f29-b5e0-ab299a1388db">IPrintOemDriverUI COM Interface</a>, which includes a <code>DrvUpgradeRegistrySetting</code> method. The behavior of this method is exactly the same as that of <a href="print.iprintoemdriverui_drvupgraderegistrysetting">IPrintOemDriverUI::DrvUpgradeRegistrySetting</a>. </p>

<p>This method should be called only by the OEM's <a href="print.iprintoemui_upgradeprinter">IPrintOemUI::UpgradePrinter</a> method.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Prcomoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.iprintoemdriverui_drvupgraderegistrysetting">IPrintOemDriverUI::DrvUpgradeRegistrySetting</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreUI2::DrvUpgradeRegistrySetting method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
