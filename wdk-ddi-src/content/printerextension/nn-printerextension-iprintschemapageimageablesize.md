---
UID: NN:printerextension.IPrintSchemaPageImageableSize
title: IPrintSchemaPageImageableSize
author: windows-driver-content
description: Exposes the PageImageableSize property of PrintCapabilities. The properties of this interface map directly to those in the PageImageableSize property of PrintCapabilities.
old-location: print\iprintschemapageimageablesize_interface.htm
old-project: print
ms.assetid: C8E9278D-D24A-4EEC-8F68-D77C76ECCC40
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print.iprintschemapageimageablesize_interface, IPrintSchemaPageImageableSize interface [Print Devices], IPrintSchemaPageImageableSize interface [Print Devices], described, IPrintSchemaPageImageableSize, printerextension/IPrintSchemaPageImageableSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrintSchemaPageImageableSize
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaPageImageableSize interface

Exposes the PageImageableSize property of PrintCapabilities. The properties of this interface map directly to those in the PageImageableSize property of PrintCapabilities.

## Methods

<p>The <b>IPrintSchemaPageImageableSize</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [printerextension.IPrintSchemaPageImageableSize.get_ExtentHeightInMicrons](nf-printerextension-iprintschemapageimageablesize-get_extentheightinmicrons.md) | Gets the vertical distance between the origin and the bounding limit of the canvas application media size. |
| [printerextension.IPrintSchemaPageImageableSize.get_ExtentWidthInMicrons](nf-printerextension-iprintschemapageimageablesize-get_extentwidthinmicrons.md) | Gets the horizontal distance between the origin and the bounding limit of the application media size. |
| [printerextension.IPrintSchemaPageImageableSize.get_ImageableSizeHeightInMicrons](nf-printerextension-iprintschemapageimageablesize-get_imageablesizeheightinmicrons.md) | Gets the vertical dimension of the application media size relative to the page orientation. |
| [printerextension.IPrintSchemaPageImageableSize.get_ImageableSizeWidthInMicrons](nf-printerextension-iprintschemapageimageablesize-get_imageablesizewidthinmicrons.md) | Gets the horizontal dimension of the application media size relative to the page orientation. |
| [printerextension.IPrintSchemaPageImageableSize.get_OriginHeightInMicrons](nf-printerextension-iprintschemapageimageablesize-get_originheightinmicrons.md) | Gets the vertical origin of the imageable area relative to the application media size. |
| [printerextension.IPrintSchemaPageImageableSize.get_OriginWidthInMicrons](nf-printerextension-iprintschemapageimageablesize-get_originwidthinmicrons.md) | Gets the horizontal origin of the imageable area relative to the application media size. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |