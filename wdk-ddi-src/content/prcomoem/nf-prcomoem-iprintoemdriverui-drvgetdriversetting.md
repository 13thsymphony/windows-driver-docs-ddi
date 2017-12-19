---
UID: NF.prcomoem.IPrintOemDriverUI.DrvGetDriverSetting
title: IPrintOemDriverUI::DrvGetDriverSetting method
author: windows-driver-content
description: The IPrintOemDriverUI::DrvGetDriverSetting method is provided by the Unidrv and Pscript5 minidrivers so that user interface plug-ins can obtain the current status of printer features and other internal information.
old-location: print\iprintoemdriverui_drvgetdriversetting.htm
old-project: print
ms.assetid: 25e8aec7-86af-4753-83d7-e7df5435f602
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintOemDriverUI, IPrintOemDriverUI::DrvGetDriverSetting, DrvGetDriverSetting
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
req.alt-api: IPrintOemDriverUI.DrvGetDriverSetting
req.alt-loc: prcomoem.h
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

# IPrintOemDriverUI::DrvGetDriverSetting method



## -description
The <code>IPrintOemDriverUI::DrvGetDriverSetting</code> method is provided by the Unidrv and Pscript5 minidrivers so that user interface plug-ins can obtain the current status of printer features and other internal information.



## -syntax

````
HRESULT DrvGetDriverSetting(
   PVOID  pci,
   PCSTR  Feature,
   PVOID  pOutput,
   DWORD  cbSize,
   PDWORD pcbNeeded,
   PDWORD pdwOptionsReturned
);
````


## -parameters

### -param pci 

Caller-supplied pointer to an <a href="print.oemuiobj">OEMUIOBJ</a> structure.


### -param Feature 

Caller-supplied value identifying the printer feature for which option settings are returned. This can be either a string pointer or a constant, as described in the following Remarks section.


### -param pOutput 

Caller-supplied pointer to a buffer to receive the specified information.


### -param cbSize 

Caller-supplied size, in bytes, of the buffer pointed to by <i>pOutput</i>.


### -param pcbNeeded 

Caller-supplied pointer to a location to receive the minimum buffer size required to contain the requested information.


### -param pdwOptionsReturned 

Caller-supplied pointer to a location to receive the number of option strings placed in <i>pOutput</i>.


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 


## -remarks
When calling the <code>IPrintOemDriverUI::DrvGetDriverSetting</code> method, a user interface plug-in can specify either a string pointer or a constant value for <i>pFeatureKeyword</i>.

If <i>pFeatureKeyword</i> is a string, it must represent one of the following:<ul>
<li>A feature name specified in a <a href="https://msdn.microsoft.com/ebf12f61-6194-4033-92a2-2bbccc40a6fd">Unidrv minidriver</a> GPD file, or,</li>
<li>A keyword argument to an *<b>OpenUI</b> entry in a Pscript5 minidriver's PPD file.</li>
</ul>


The method returns one or more NULL-terminated strings in the buffer pointed to by <i>pOutput</i>. Each string represents the name of a currently selected option.The number of strings is returned in <i>pdwOptionsReturned</i>.

If <i>pFeatureKeyword</i> is a constant, it must be one of the <b>OEMGDS_</b>-prefixed constants defined in printoem.h. The method returns the value indicated by the specified constant by placing it in the buffer pointed to by <i>pOutput</i>. The value returned in <i>pdwOptionsReturned</i> is always 1.


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
<dt>Prcomoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>