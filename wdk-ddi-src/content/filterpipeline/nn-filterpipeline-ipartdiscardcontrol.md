---
UID: NN:filterpipeline.IPartDiscardControl
title: IPartDiscardControl
author: windows-driver-content
description: The filter pipeline supports the discard control.
old-location: print\ipartdiscardcontrol.htm
old-project: print
ms.assetid: 30c6fb0c-42ea-441f-b0a2-3310f8a5b407
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPartDiscardControl, IPartDiscardControl interface [Print Devices], IPartDiscardControl interface [Print Devices], described, filterpipeline/IPartDiscardControl, filterpipeline_c29b91d3-ecf6-4697-bf5f-5b536cfb7071.xml, print.ipartdiscardcontrol
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IPartDiscardControl
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPartDiscardControl interface

The filter pipeline supports the discard control. Filters can use this object, if they obtain it from <a href="https://msdn.microsoft.com/library/windows/hardware/ff556324">IXpsDocumentProvider::GetXpsPart</a> method. In some cases, processing this object might just include forwarding it to the next filter by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556314">IXpsDocumentConsumer::SendXpsUnknown</a> method.

Filters can also create discard controls. To create a discard control, the filter must create an object that implements the <b>IPartDiscardControl</b> interface. Because the filter transfers ownership of the discard control when it sends it to the next filter, the filter must manage the lifetime of the discard control. If a filter creates a discard control, the filter DLL must not unload until the discard control has been released.

## Methods

<p>The <b>IPartDiscardControl</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [IPartDiscardControl::GetDiscardProperties](nf-filterpipeline-ipartdiscardcontrol-getdiscardproperties.md) | The GetDiscardProperties method gets the properties of the discard control. |


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | filterpipeline.h (include Filterpipeline.h) |