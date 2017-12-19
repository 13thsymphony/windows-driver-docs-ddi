---
UID: NF.prcomoem.IPrintOemUni.ResetPDEV
title: IPrintOemUni::ResetPDEV method
author: windows-driver-content
description: The IPrintOemUni::ResetPDEV method allows a rendering plug-in for Unidrv to reset its PDEV structure.
old-location: print\iprintoemuni_resetpdev.htm
old-project: print
ms.assetid: 7398a265-56e0-4b40-bfbb-0d72e7309efc
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintOemUni, IPrintOemUni::ResetPDEV, ResetPDEV
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
req.alt-api: IPrintOemUni.ResetPDEV
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
req.product: Windows 10 or later.
---

# IPrintOemUni::ResetPDEV method



## -description
The <code>IPrintOemUni::ResetPDEV</code> method allows a rendering plug-in for Unidrv to reset its PDEV structure.



## -syntax

````
STDMETHOD ResetPDEV(
   PDEVOBJ pdevobjOld,
   PDEVOBJ pdevobjNew
);
````


## -parameters

### -param pdevobjOld 

Caller-supplied pointer to a <a href="print.devobj">DEVOBJ</a> structure containing current PDEV information.


### -param pdevobjNew 

Caller-supplied pointer to a DEVOBJ structure into which the method should place new PDEV information.


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed.

 

If the operation fails, this method should call <b>SetLastError</b>.


## -remarks
A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::ResetPDEV</code> method.

A rendering plug-in's <code>IPrintOemUni::ResetPDEV</code> method performs the same types of operations as the <a href="display.drvresetpdev">DrvResetPDEV</a> function that is exported by a printer graphics DLL. During the processing of an application's call to the Microsoft Windows SDK <b>ResetDC</b> function, the <code>IPrintOemUni::ResetPDEV</code> method is called by the <b>DrvResetPDEV</b> function in Unidrv's printer graphics DLL. For more information about when <b>DrvResetPDEV</b> is called, see its description.

The rendering plug-in's private PDEV structure's address is contained in the <b>pdevOEM</b> member of the DEVOBJ structure pointed to by <i>pdevobjOld</i>. The <code>IPrintOemUni::ResetPDEV</code> method should use relevant members of this old structure to fill in the new structure, which is referenced through <i>pdevobjNew</i>.


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

## -see-also
<dl>
<dt>
<a href="display.drvresetpdev">DrvResetPDEV</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUni::ResetPDEV method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

