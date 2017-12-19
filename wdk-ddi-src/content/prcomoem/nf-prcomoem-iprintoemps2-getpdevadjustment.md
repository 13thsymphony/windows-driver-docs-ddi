---
UID: NF.prcomoem.IPrintOemPS2.GetPDEVAdjustment
title: IPrintOemPS2::GetPDEVAdjustment method
author: windows-driver-content
description: The IPrintOemPS2::GetPDEVAdjustment method enables a plug-in to override specific PDEV settings.
old-location: print\iprintoemps2_getpdevadjustment.htm
old-project: print
ms.assetid: 8dc4252f-72d5-47ae-9f43-8006aa71c29d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintOemPS2, IPrintOemPS2::GetPDEVAdjustment, GetPDEVAdjustment
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
req.alt-api: IPrintOemPS2.GetPDEVAdjustment
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

# IPrintOemPS2::GetPDEVAdjustment method



## -description
The <code>IPrintOemPS2::GetPDEVAdjustment</code> method enables a plug-in to override specific <a href="wdkgloss.p#wdkgloss.pdev#wdkgloss.pdev"><i>PDEV</i></a> settings.



## -syntax

````
HRESULT GetPDEVAdjustment(
        PDEVOBJ pdevobj,
        DWORD   dwAdjustType,
        PVOID   pBuf,
        DWORD   cbBuffer,
  [out] BOOL    *pbAdjustmentDone
);
````


## -parameters

### -param pdevobj 

Pointer to a <a href="print.devobj">DEVOBJ</a> structure.


### -param dwAdjustType 

Specifies the type of adjustment asked for. The following flags are currently supported:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PDEV_ADJUST_PAPER_MARGIN_TYPE

</td>
<td>
Adjust the paper margin setting that is reported in the PDEV. See the <a href="print.pdev_adjust_paper_margin">PDEV_ADJUST_PAPER_MARGIN</a> structure.

</td>
</tr>
<tr>
<td>
PDEV_HOSTFONT_ENABLED_TYPE

</td>
<td>
Enable or disable the Hostfont support feature. See the <a href="print.pdev_hostfont_enabled">PDEV_HOSTFONT_ENABLED</a> structure.

</td>
</tr>
<tr>
<td>
PDEV_USE_TRUE_COLOR_TYPE

</td>
<td>
Enable or disable color output for monochrome and color printers. See the <a href="print.pdev_use_true_color">PDEV_USE_TRUE_COLOR</a> structure.

</td>
</tr>
</table>
 


### -param pBuf 

Pointer to a structure that contains the planned settings that are used if there is no change. These structures are listed in the preceding table. The plug-in can overwrite the settings in the relevant structure.


### -param cbBuffer 

Specifies the size, in bytes, of the structure pointed to by <i>pBuf</i>.


### -param pbAdjustmentDone [out]

Pointer to a memory location that the plug-in sets to <b>TRUE</b> when it actually changes a value in the buffer. This may be used by the driver for optimizations.


## -returns
The <code>IPrintOemPS2::GetPDEVAdjustment</code> method should return S_OK if it recognizes the adjustment type, and S_FALSE if it does not. If the method fails, it should return E_FAIL. The chain of plug-ins is called until either S_OK or a failure code other than E_NOTIMPL is returned. That is, the chain of plug-ins is called until the first plug-in that is capable of handling the adjustment is found.


## -remarks
This function is available in Windows XP and later.

Currently, the Pscript5 driver calls <code>IPrintOemPS2::GetPDEVAdjustment</code> to adjust the paper margin setting, as reported in the PDEV, to enable or disable the Hostfont feature, or to turn PostScript color output on or off. 


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
<a href="print.pdev_adjust_paper_margin">PDEV_ADJUST_PAPER_MARGIN</a>
</dt>
<dt>
<a href="print.pdev_hostfont_enabled">PDEV_HOSTFONT_ENABLED</a>
</dt>
<dt>
<a href="print.pdev_use_true_color">PDEV_USE_TRUE_COLOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemPS2::GetPDEVAdjustment method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

