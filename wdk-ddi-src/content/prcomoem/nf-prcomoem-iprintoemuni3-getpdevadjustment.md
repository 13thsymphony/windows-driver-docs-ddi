---
UID: NF:prcomoem.IPrintOemUni3.GetPDEVAdjustment
title: IPrintOemUni3::GetPDEVAdjustment method
author: windows-driver-content
description: The IPrintOemUni3::GetPDEVAdjustment method enables a plug-in to override specific PDEV settings.
old-location: print\iprintoemuni3_getpdevadjustment.htm
old-project: print
ms.assetid: bb7d7248-9520-4bc8-8483-b05b78608fc7
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemUni3, IPrintOemUni3::GetPDEVAdjustment, GetPDEVAdjustment
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
req.alt-api: IPrintOemUni3.GetPDEVAdjustment
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUni3::GetPDEVAdjustment method



## -description
The <code>IPrintOemUni3::GetPDEVAdjustment</code> method enables a plug-in to override specific <a href="wdkgloss.p#wdkgloss.pdev#wdkgloss.pdev"><i>PDEV</i></a> settings.



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

Pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param dwAdjustType 

Specifies the type of adjustment asked for. The following flags are currently supported.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PDEV_ADJUST_GRAPHICS_RESOLUTION_TYPE

</td>
<td>
Adjust the graphics resolution setting that is reported in the PDEV structure. For more information, see the <a href="..\printoem\ns-printoem-_pdev_adjust_graphics_resolution.md">PDEV_ADJUST_GRAPHICS RESOLUTION</a> structure.

</td>
</tr>
<tr>
<td>
PDEV_IMAGEABLE_ORIGIN_AREA_TYPE

</td>
<td>
Adjust the imageable origin area that is reported in the PDEV structure. For more information, see the <a href="..\printoem\ns-printoem-_pdev_adjust_imageable_origin_area.md">PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA</a> structure.

</td>
</tr>
<tr>
<td>
PDEV_ADJUST_PHYSICAL_PAPER_SIZE_TYPE

</td>
<td>
Adjust the physical paper size that is reported in the PDEV structure. For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559796">PDEV_ADJUST_PAPER_PHYSICAL_SIZE</a> structure.

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
The <code>IPrintOemUni3::GetPDEVAdjustment</code> method should return S_OK if it recognizes the adjustment type, and S_FALSE if it does not. If the method fails, it should return E_FAIL. The chain of plug-ins is called until either S_OK or a failure code other than E_NOTIMPL is returned. That is, the chain of plug-ins is called until the first plug-in that is capable of handling the adjustment is found.


## -remarks
This function is available in Windows Vista and later.

Currently, the Unidrv driver calls <code>IPrintOemUni3::GetPDEVAdjustment</code> to adjust the graphics resolution setting, as reported in the PDEV, to adjust the imageable origin area, or to adjust the physical paper size.


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
<a href="..\printoem\ns-printoem-_pdev_adjust_graphics_resolution.md">PDEV_ADJUST_GRAPHICS RESOLUTION</a>
</dt>
<dt>
<a href="..\printoem\ns-printoem-_pdev_adjust_imageable_origin_area.md">PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA</a>
</dt>
<dt>
<a href="..\printoem\ns-printoem-_pdev_adjust_paper_margin.md">PDEV_ADJUST_PAPER_MARGIN</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559796">PDEV_ADJUST_PAPER_PHYSICAL_SIZE</a>
</dt>
<dt>
<a href="..\printoem\ns-printoem-_pdev_hostfont_enabled.md">PDEV_HOSTFONT_ENABLED</a>
</dt>
<dt>
<a href="..\printoem\ns-printoem-_pdev_use_true_color.md">PDEV_USE_TRUE_COLOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUni3::GetPDEVAdjustment method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

