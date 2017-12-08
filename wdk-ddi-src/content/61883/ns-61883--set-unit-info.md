---
UID: NS.61883._SET_UNIT_INFO
title: SET_UNIT_INFO
author: windows-driver-content
description: This structure is used to set unit information.
old-location: ieee\set_unit_info.htm
old-project: IEEE
ms.assetid: D4A9B507-E199-42EA-BC29-6F477BEC8D20
ms.author: windowsdriverdev
ms.date: 11/29/2017
ms.keywords: SET_UNIT_INFO, SET_UNIT_INFO, *PSET_UNIT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SET_UNIT_INFO
req.alt-loc: 61883.h
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

# SET_UNIT_INFO structure



## -description
<p>This structure is used to set unit information.</p>
<p>The Av61883_SetUnitInfo request sets the parameters that the IEC-61883 protocol driver should use when capturing and transmitting isochronous packets. </p>


## -syntax

````
typedef struct _SET_UNIT_INFO {
  ULONG nLevel;
  PVOID Information;
} SET_UNIT_INFO, *PSET_UNIT_INFO;
````


## -struct-fields
<dl>

### -field nLevel

<dd>
<p>On input, the level of information to retrieve. Can be one of the following:</p>
<p>SET_UNIT_INFO_DIAG_LEVEL</p>
<p>SET_UNIT_INFO_ISOCH_PARAMS</p>
<p>SET_CMP_ADDRESS_RANGE_TYPE</p>
</dd>

### -field Information

<dd>
<p>On input, if <b>nLevel</b> is SET_UNIT_INFO_DIAG_LEVEL, this member is a pointer to a caller-allocated and initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff538914">UNIT_DIAG_LEVEL</a> structure.</p>
<p>If <b>nLevel</b> is SET_UNIT_INFO_ISOCH_PARAMS, this member is a pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff538921">UNIT_ISOCH_PARAMS</a> structure. </p>
<p>If <b>nLevel</b> is SET_CMP_ADDRESS_RANGE_TYPE, this member is a pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff538118">SET_CMP_ADDRESS_TYPE</a> structure. </p>
</dd>
</dl>

## -remarks
<p>If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. </p>

<p>If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>61883.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20SET_UNIT_INFO structure%20 RELEASE:%20(11/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
