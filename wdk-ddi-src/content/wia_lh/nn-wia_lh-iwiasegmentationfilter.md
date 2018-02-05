---
UID : NN:wia_lh.IWiaSegmentationFilter
title : IWiaSegmentationFilter
author : windows-driver-content
description : The IWiaSegmentationFilter interface provides the DetectRegions method, which enables minidrivers to detect image subregions on a flatbed scanner's platen. This interface is available in Windows Vista and later.
old-location : image\iwiasegmentationfilter_interface.htm
old-project : image
ms.assetid : 93f2942b-3c01-43e7-9b8a-9542ab7bfd74
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : image.iwiasegmentationfilter_interface, IWiaSegmentationFilter interface [Imaging Devices], IWiaSegmentationFilter interface [Imaging Devices], described, IWiaSegmentationFilter, wia_lh/IWiaSegmentationFilter, iwiasegmentationfilter_24576c71-3e48-4152-bbd2-d3722d07a283.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : wia_lh.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : wia_lh.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product : Windows 10 or later.
---

# IWiaSegmentationFilter interface

The <b>IWiaSegmentationFilter</b> interface provides the <a href="https://msdn.microsoft.com/53ad769e-38b5-463d-9fa0-053c2215cc81">DetectRegions</a> method, which enables minidrivers to detect image subregions on a flatbed scanner's platen. This interface is available in Windows Vista and later.

## Methods

<p>The <b>IWiaSegmentationFilter</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [wia_lh.IWiaSegmentationFilter.DetectRegions](nf-wia_lh-iwiasegmentationfilter-detectregions.md) | The IWiaSegmentationFilter::DetectRegions method determines the subregions of an image laid out on the flatbed platen so that each subregion can be acquired into a separate image item. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wia_lh.h |