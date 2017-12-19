---
UID: NE.d3d12umddi.D3D12DDI_TABLE_TYPE
title: D3D12DDI_TABLE_TYPE
author: windows-driver-content
description: Command list and queue types to allow drivers to point to different implementations for video.
old-location: display\d3d12ddi_table_type.htm
old-project: display
ms.assetid: 93562C36-7ADE-4CC6-B33D-D6E955E3D42C
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D12DDI_TABLE_TYPE, D3D12DDI_TABLE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_TABLE_TYPE
req.alt-loc: D3d12umddi.h
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
---

# D3D12DDI_TABLE_TYPE enumeration



## -description
Command list and queue types to allow drivers to point to different implementations for video.



## -syntax

````
typedef enum D3D12DDI_TABLE_TYPE { 
  D3D12DDI_TABLE_TYPE_DEVICE_CORE                               = 0,
  D3D12DDI_TABLE_TYPE_COMMAND_LIST_3D                           = 1,
  D3D12DDI_TABLE_TYPE_COMMAND_QUEUE_3D                          = 2,
  D3D12DDI_TABLE_TYPE_DXGI                                      = 3,
  D3D12DDI_TABLE_TYPE_0020_DEVICE_VIDEO                         = 4,
  D3D12DDI_TABLE_TYPE_0020_DEVICE_CORE_VIDEO                    = 7,
  D3D12DDI_TABLE_TYPE_0020_EXTENDED_FEATURES                    = 8,
  D3D12DDI_TABLE_TYPE_0020_PASS_EXPERIMENT                      = 9,
  D3D12DDI_TABLE_TYPE_0021_SHADERCACHE_CALLBACKS                = 10,
  D3D12DDI_TABLE_TYPE_0022_COMMAND_QUEUE_VIDEO_DECODE           = 11,
  D3D12DDI_TABLE_TYPE_0022_COMMAND_LIST_VIDEO_DECODE            = 12,
  D3D12DDI_TABLE_TYPE_0022_COMMAND_QUEUE_VIDEO_PROCESS          = 13,
  D3D12DDI_TABLE_TYPE_0022_COMMAND_LIST_VIDEO_PROCESS           = 14,
  D3D12DDI_TABLE_TYPE_0030_DEVICE_CONTENT_PROTECTION_RESOURCES  = 15,
  D3D12DDI_TABLE_TYPE_0030_CONTENT_PROTECTION_CALLBACKS         = 16,
  D3D12DDI_TABLE_TYPE_0030_DEVICE_CONTENT_PROTECTION_STREAMING  = 17
} D3D12DDI_TABLE_TYPE;
````


## -enum-fields

### -field D3D12DDI_TABLE_TYPE_DEVICE_CORE

Device core.


### -field D3D12DDI_TABLE_TYPE_COMMAND_LIST_3D

List 3D.


### -field D3D12DDI_TABLE_TYPE_COMMAND_QUEUE_3D

Queue 3D.


### -field D3D12DDI_TABLE_TYPE_DXGI

DXGI.


### -field D3D12DDI_TABLE_TYPE_0020_DEVICE_VIDEO

Device video.


### -field D3D12DDI_TABLE_TYPE_0020_DEVICE_CORE_VIDEO

Queue video.


### -field D3D12DDI_TABLE_TYPE_0020_EXTENDED_FEATURES

Extended features.


### -field D3D12DDI_TABLE_TYPE_0020_PASS_EXPERIMENT

Pass experiment.


### -field D3D12DDI_TABLE_TYPE_0021_SHADERCACHE_CALLBACKS

Shader cache callbacks.


### -field D3D12DDI_TABLE_TYPE_0022_COMMAND_QUEUE_VIDEO_DECODE

Queue video decode.


### -field D3D12DDI_TABLE_TYPE_0022_COMMAND_LIST_VIDEO_DECODE

List video decode.


### -field D3D12DDI_TABLE_TYPE_0022_COMMAND_QUEUE_VIDEO_PROCESS

Queue video process.


### -field D3D12DDI_TABLE_TYPE_0022_COMMAND_LIST_VIDEO_PROCESS

List video process.


### -field D3D12DDI_TABLE_TYPE_0030_DEVICE_CONTENT_PROTECTION_RESOURCES

Device content protection resources.


### -field D3D12DDI_TABLE_TYPE_0030_CONTENT_PROTECTION_CALLBACKS

Content protection callbacks.


### -field D3D12DDI_TABLE_TYPE_0030_DEVICE_CONTENT_PROTECTION_STREAMING

Device content protection streaming.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>