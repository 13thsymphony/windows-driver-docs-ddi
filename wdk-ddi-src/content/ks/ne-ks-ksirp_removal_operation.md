---
UID: NE:ks.KSIRP_REMOVAL_OPERATION
title: KSIRP_REMOVAL_OPERATION
author: windows-driver-content
description: "."
old-location: stream\ksirp_removal_operation.htm
old-project: stream
ms.assetid: 10AC7347-6C6B-4A37-9298-B773ADCB3FDA
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KSIRP_REMOVAL_OPERATION, KSIRP_REMOVAL_OPERATION enumeration [Streaming Media Devices], KsAcquireAndRemove, KsAcquireAndRemoveOnlySingleItem, KsAcquireOnly, KsAcquireOnlySingleItem, ks/KSIRP_REMOVAL_OPERATION, ks/KsAcquireAndRemove, ks/KsAcquireAndRemoveOnlySingleItem, ks/KsAcquireOnly, ks/KsAcquireOnlySingleItem, stream.ksirp_removal_operation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ks.h
api_name:
-	KSIRP_REMOVAL_OPERATION
product: Windows
targetos: Windows
req.typenames: KSIRP_REMOVAL_OPERATION
---

# KSIRP_REMOVAL_OPERATION Enumeration


## Syntax
````
typedef enum  { 
  KsAcquireOnly,
  KsAcquireAndRemove,
  KsAcquireOnlySingleItem,
  KsAcquireAndRemoveOnlySingleItem
} KSIRP_REMOVAL_OPERATION;
````

## Constants

<table>
            
                <tr>
                    <td>KsAcquireAndRemove</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KsAcquireAndRemoveOnlySingleItem</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KsAcquireOnly</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KsAcquireOnlySingleItem</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h |