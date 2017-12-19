---
UID: NS.PCIVIRT._SRIOV_MITIGATED_RANGE_UPDATE_INPUT
title: _SRIOV_MITIGATED_RANGE_UPDATE_INPUT
author: windows-driver-content
description: This structure is used as an input buffer to the IOCTL_SRIOV_MITIGATED_RANGE_UPDATE request to indicate the virtual function (VF) whose memory-mapped I/O space that must be mitigated.
old-location: pci\sriov_mitigated_range_update_input.htm
old-project: PCI
ms.assetid: ae4936ac-9794-4854-81ec-2139b3ce4c3c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SRIOV_MITIGATED_RANGE_UPDATE_INPUT, SRIOV_MITIGATED_RANGE_UPDATE_INPUT, *PSRIOV_MITIGATED_RANGE_UPDATE_INPUT, PSRIOV_MITIGATED_RANGE_UPDATE_INPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pcivirt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SRIOV_MITIGATED_RANGE_UPDATE_INPUT
req.alt-loc: pcivirt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _SRIOV_MITIGATED_RANGE_UPDATE_INPUT structure



## -description
This structure is used as an input buffer to the <a href="buses.ioctl_sriov_mitigated_range_update">IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</a> request to indicate the virtual function (VF) whose memory-mapped I/O space that must be mitigated. 



## -syntax

````
typedef struct _SRIOV_MITIGATED_RANGE_UPDATE_INPUT {
  USHORT  VfIndex;
} SRIOV_MITIGATED_RANGE_UPDATE_INPUT, SRIOV_MITIGATED_RANGE_UPDATE_INPUT;
````


## -struct-fields

### -field VfIndex

Zero-based index of the virtual function from the first virtual function exposed by this physical function.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Pcivirt.h</dt>
</dl>
</td>
</tr>
</table>