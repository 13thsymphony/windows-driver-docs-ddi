---
UID : NS:d3dkmthk._D3DKMT_SEGMENTGROUPSIZEINFO
title : _D3DKMT_SEGMENTGROUPSIZEINFO
author : windows-driver-content
description : A structure that holds information about the segment group size.
old-location : display\d3dkmt_segmentgroupsizeinfo.htm
old-project : display
ms.assetid : 4D9D8179-AA55-409B-A733-7346EC06391B
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.d3dkmt_segmentgroupsizeinfo, D3DKMT_SEGMENTGROUPSIZEINFO, D3DKMT_SEGMENTGROUPSIZEINFO structure [Display Devices], d3dkmthk/D3DKMT_SEGMENTGROUPSIZEINFO, _D3DKMT_SEGMENTGROUPSIZEINFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmthk.h
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
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DKMT_SEGMENTGROUPSIZEINFO
---

# _D3DKMT_SEGMENTGROUPSIZEINFO structure
A structure that holds information about the segment group size.

## Syntax
````
typedef struct _D3DKMT_SEGMENTGROUPSIZEINFO {
  UINT32                 PhysicalAdapterIndex;
  D3DKMT_SEGMENTSIZEINFO LegacyInfo;
  ULONGLONG              LocalMemory;
  ULONGLONG              NonLocalMemory;
  ULONGLONG              NonBudgetMemory;
} D3DKMT_SEGMENTGROUPSIZEINFO;
````

## Members


`LegacyInfo`

Legacy segment size info.

`LocalMemory`

The size of local memory.

`NonBudgetMemory`

The size of non-budget memory.

`NonLocalMemory`

The size of non-local memory.

`PhysicalAdapterIndex`

An index to the physical adapter.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h |