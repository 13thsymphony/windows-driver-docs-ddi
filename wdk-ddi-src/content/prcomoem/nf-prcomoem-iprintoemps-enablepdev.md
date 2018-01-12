---
UID: NF:prcomoem.IPrintOemPS.EnablePDEV
title: IPrintOemPS::EnablePDEV method
author: windows-driver-content
description: The IPrintOemPS::EnablePDEV method allows a rendering plug-in for Pscript5 to create its own PDEV structure.
old-location: print\iprintoemps_enablepdev.htm
old-project: print
ms.assetid: f284e89f-463e-4d04-8018-5ce02786d921
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemPS, IPrintOemPS::EnablePDEV, EnablePDEV
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
req.alt-api: IPrintOemPS.EnablePDEV
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

# IPrintOemPS::EnablePDEV method



## -description
The <code>IPrintOemPS::EnablePDEV</code> method allows a rendering plug-in for Pscript5 to create its own PDEV structure.



## -syntax

````
STDMETHOD EnablePDEV(
        PDEVOBJ       pdevobj,
        PWSTR         pPrinterName,
        ULONG         cPatterns,
        HSURF         *phsurfPatterns,
        ULONG         cjGdiInfo,
        GDIINFO       *pGdiInfo,
        ULONG         cjDevInfo,
        DEVINFO       *pDevInfo,
        DRVENABLEDATA *pded,
  [out] PDEVOEM       *pDevOem
);
````


## -parameters

### -param pdevobj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param pPrinterName 

Caller-supplied pointer to a text string representing the logical address of the printer.


### -param cPatterns 

Caller-supplied value representing the number of HSURF-typed surface handles contained in the buffer pointed to by <i>phsurfPatterns</i>.


### -param phsurfPatterns 

Caller-supplied pointer to a buffer that is large enough to contain <i>cPatterns</i> number of HSURF-typed surface handles. The handles represent surface fill patterns.


### -param cjGdiInfo 

Caller-supplied value representing the size of the structure pointed to by <i>pGdiInfo</i>.


### -param pGdiInfo 

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566484">GDIINFO</a> structure.


### -param cjDevInfo 

Caller-supplied value representing the size of the structure pointed to by <i>pDevInfo</i>.


### -param pDevInfo 

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552835">DEVINFO</a> structure.


### -param pded 

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556206">DRVENABLEDATA</a> structure containing the addresses of the printer driver's graphics DDI hooking functions. For more information, see the following Remarks section.


### -param pDevOem [out]

Receives a method-supplied pointer to a private PDEV structure. (For more information, see the following Remarks section.)


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 

If the operation fails, the method should call <b>SetLastError</b> to set an error code.


## -remarks
The <code>IPrintOemPS::EnablePDEV</code> method performs the same types of operations as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a> function that is exported by a printer graphics DLL. Its purpose is to allow a rendering plug-in to create its own PDEV structure. (For more information about PDEV structures, see <a href="https://msdn.microsoft.com/e5c51b9a-5f73-4411-88d8-931981a8450c">Customized PDEV Structures</a>.)

If you provide a rendering plug-in that exports the <code>IPrintOemPS::EnablePDEV</code> method, Pscript5's printer graphics DLL calls the method from within its <a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a> function. 

The <code>IPrintOemPS::EnablePDEV</code> method should allocate an instance of its private PDEV structure, initialize it, and return its address as the method's <i>pDevOem</i> parameter. Other plug-in methods receive the address as the <b>pdevOEM</b> member of the <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.

The <b>pdevOEM</b> member of the DEVOBJ structure is not used with the <code>IPrintOemPS::EnablePDEV</code> method.

The structures pointed to by the <i>phsurfPatterns</i>, <i>pGdiInfo</i>, and <i>pDevInfo</i> parameter values are the same ones that Pscript5's <b>DrvEnablePDEV</b> function receives. The rendering plug-in can modify the structure contents as necessary. It can supply surface fill patterns by obtaining HSURF-typed surface handles and placing them in the buffer pointed to by <i>phsurfPatterns</i>. Fill pattern types and handle order are listed in the description of <a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a>.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff556206">DRVENABLEDATA</a> structure pointed to by <i>pded</i> contains the addresses of graphics DDI functions provided by Pscript5's printer graphics DLL. You are allowed to provide customized hooking functions in your plug-in for these graphics DDI functions. The DRVENABLEDATA structure's contents enable your customized hooking functions to call back to the driver's graphics DDI functions. For more information, see <a href="https://msdn.microsoft.com/33d7d567-5371-4873-a4ef-cd2b06f65d73">Customized Graphics DDI Functions</a>.


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