---
UID: NN.xpsrassvc.IXpsRasterizationFactory2
title: IXpsRasterizationFactory2
author: windows-driver-content
description: In Windows 10, the IXpsRasterizationFactory2 interface represents an object factory for creating components that can convert content from XPS to PWG Raster using the XPS Rasterization Service. PWG Raster supports non-square DPIs.
old-location: print\ixpsrasterizationfactory2.htm
old-project: print
ms.assetid: 23994CD9-A65B-4BD7-9070-3F575D011953
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: __MIDL___MIDL_itf_xpsrassvc_0000_0004_0001, XPSRAS_BACKGROUND_COLOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: xpsrassvc.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IXpsRasterizationFactory2
req.alt-loc: xpsrassvc.h
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

# IXpsRasterizationFactory2 interface



## -description
In Windows 10, the <b>IXpsRasterizationFactory2</b> interface represents an object factory for creating components that can  convert content from XPS to PWG Raster using the <a href="print.xps_rasterization_service_reference">XPS Rasterization Service</a>. PWG Raster supports non-square DPIs.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IXpsRasterizationFactory2</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IXpsRasterizationFactory2</b> also has these types of members:

The <b>IXpsRasterizationFactory2</b> interface has these methods.

The <b>CreateRasterizer</b> method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the <a href="print.xps_rasterization_service_reference">XPS Rasterization Service</a>. PWG Raster supports non-square DPIs.


 


## -members
The <b>IXpsRasterizationFactory2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.ixpsrasterizationfactory2_createrasterizer">CreateRasterizer</a>
</td>
<td align="left" width="63%">
The <b>CreateRasterizer</b> method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the <a href="print.xps_rasterization_service_reference">XPS Rasterization Service</a>. PWG Raster supports non-square DPIs.


</td>
</tr>
</table>The <b>CreateRasterizer</b> method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the <a href="print.xps_rasterization_service_reference">XPS Rasterization Service</a>. PWG Raster supports non-square DPIs.


 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Xpsrassvc.h</dt>
</dl>
</td>
</tr>
</table>