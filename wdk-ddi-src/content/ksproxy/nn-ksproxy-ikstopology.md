---
UID: NN:ksproxy.IKsTopology
title: IKsTopology
author: windows-driver-content
description: The IKsTopology interface provides a method that opens topology node objects contained within a filter.
old-location: stream\ikstopology.htm
old-project: stream
ms.assetid: 418a415c-b4db-41a1-825e-66704c45e134
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ikstopology, IKsTopology interface [Streaming Media Devices], IKsTopology interface [Streaming Media Devices], described, IKsTopology, ksproxy/IKsTopology, ksproxy_521e5b73-c9cc-4cb2-acf5-746e470678cd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: ksproxy.h
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
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ksproxy.h
apiname:
-	IKsTopology
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsTopology interface

The <b>IKsTopology</b> interface provides a method that opens topology node objects contained within a filter.

## Methods

<p>The <b>IKsTopology</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [ksproxy.IKsTopology.CreateNodeInstance](nf-ksproxy-ikstopology-createnodeinstance.md) | The CreateNodeInstance method requests a KS filter object to open a topology node object. |

## Remarks

The IID for this interface is IID_IKsTopology.

The <b>IKsTopology</b> interface is supported by filters.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ksproxy.h |