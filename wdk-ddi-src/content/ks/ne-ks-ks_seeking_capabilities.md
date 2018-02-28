---
UID: NE:ks.KS_SEEKING_CAPABILITIES
title: KS_SEEKING_CAPABILITIES
author: windows-driver-content
description: "."
old-location: stream\ks_seeking_capabilities.htm
old-project: stream
ms.assetid: 345ADD1F-2002-4F9C-942C-212CADCF84E5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KS_SEEKING_CAPABILITIES, KS_SEEKING_CAPABILITIES enumeration [Streaming Media Devices], KS_SEEKING_CanGetCurrentPos, KS_SEEKING_CanGetDuration, KS_SEEKING_CanGetStopPos, KS_SEEKING_CanPlayBackwards, KS_SEEKING_CanSeekAbsolute, KS_SEEKING_CanSeekBackwards, KS_SEEKING_CanSeekForwards, ks/KS_SEEKING_CAPABILITIES, ks/KS_SEEKING_CanGetCurrentPos, ks/KS_SEEKING_CanGetDuration, ks/KS_SEEKING_CanGetStopPos, ks/KS_SEEKING_CanPlayBackwards, ks/KS_SEEKING_CanSeekAbsolute, ks/KS_SEEKING_CanSeekBackwards, ks/KS_SEEKING_CanSeekForwards, stream.ks_seeking_capabilities
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
-	KS_SEEKING_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: KS_SEEKING_CAPABILITIES
---

# KS_SEEKING_CAPABILITIES Enumeration


## Syntax
````
typedef enum  { 
  KS_SEEKING_CanSeekAbsolute   = 0x1,
  KS_SEEKING_CanSeekForwards   = 0x2,
  KS_SEEKING_CanSeekBackwards  = 0x4,
  KS_SEEKING_CanGetCurrentPos  = 0x8,
  KS_SEEKING_CanGetStopPos     = 0x10,
  KS_SEEKING_CanGetDuration    = 0x20,
  KS_SEEKING_CanPlayBackwards  = 0x40
} KS_SEEKING_CAPABILITIES;
````

## Constants

<table>
            
                <tr>
                    <td>KS_SEEKING_CanGetCurrentPos</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KS_SEEKING_CanGetDuration</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KS_SEEKING_CanGetStopPos</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KS_SEEKING_CanPlayBackwards</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KS_SEEKING_CanSeekAbsolute</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KS_SEEKING_CanSeekBackwards</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KS_SEEKING_CanSeekForwards</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h |