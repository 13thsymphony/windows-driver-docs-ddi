---
UID: NF:prcomoem.IPrintOemPS.DevMode
title: IPrintOemPS::DevMode method
author: windows-driver-content
description: The IPrintOemPS::DevMode method, provided by rendering plug-ins for Pscript5, performs operations on private DEVMODEW members.
old-location: print\iprintoemps_devmode.htm
old-project: print
ms.assetid: 72775113-435c-44cf-83e7-9aa62f7f252e
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemPS, IPrintOemPS::DevMode, DevMode
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
req.alt-api: IPrintOemPS.DevMode
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemPS::DevMode method



## -description
The <code>IPrintOemPS::DevMode</code> method, provided by rendering plug-ins for Pscript5, performs operations on private <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> members.



## -syntax

````
STDMETHOD DevMode(
   DWORD       dwMode,
   POEMDMPARAM pOemDMParam
);
````


## -parameters

### -param dwMode 

Caller-supplied constant. See the following Remarks section.


### -param pOemDMParam 

Caller-supplied pointer to an <a href="..\printoem\ns-printoem-_oemdmparam.md">OEMDMPARAM</a> structure.


## -returns
This method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 


## -remarks
If you are providing a user interface plug-in for Pscript5, and if you are adding private members to the driver's DEVMODEW structure, you must implement both the <code>IPrintOemUI::DevMode</code> and the <code>IPrintOemPS::DevMode</code> methods. The code implementing these methods must be identical and can be placed in a library that is statically linked to both the UI plug-in and the rendering plug-in.

For a description of the <code>IPrintOemPS::DevMode</code> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554167">IPrintOemUI::DevMode</a>.


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