---
UID: NN:xpsrassvc.IXpsRasterizationFactory2
title: IXpsRasterizationFactory2
author: windows-driver-content
description: In Windows 10, the IXpsRasterizationFactory2 interface represents an object factory for creating components that can convert content from XPS to PWG Raster using the XPS Rasterization Service. PWG Raster supports non-square DPIs.
old-location: print\ixpsrasterizationfactory2.htm
old-project: print
ms.assetid: 23994CD9-A65B-4BD7-9070-3F575D011953
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.ixpsrasterizationfactory2, IXpsRasterizationFactory2 interface [Print Devices], IXpsRasterizationFactory2 interface [Print Devices], described, IXpsRasterizationFactory2, xpsrassvc/IXpsRasterizationFactory2
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: xpsrassvc.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	xpsrassvc.h
apiname:
-	IXpsRasterizationFactory2
product: Windows
targetos: Windows
req.typenames: XPSRAS_BACKGROUND_COLOR
req.product: Windows 10 or later.
---

# IXpsRasterizationFactory2 interface

In Windows 10, the <b>IXpsRasterizationFactory2</b> interface represents an object factory for creating components that can  convert content from XPS to PWG Raster using the <a href="https://msdn.microsoft.com/a0493b5f-d6f7-4f69-9c6e-e112c29250c9">XPS Rasterization Service</a>. PWG Raster supports non-square DPIs.

## Methods

<p>The <b>IXpsRasterizationFactory2</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [xpsrassvc.IXpsRasterizationFactory2.CreateRasterizer](nf-xpsrassvc-ixpsrasterizationfactory2-createrasterizer.md) | The CreateRasterizer method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the XPS Rasterization Service. PWG Raster supports non-square DPIs. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | xpsrassvc.h |