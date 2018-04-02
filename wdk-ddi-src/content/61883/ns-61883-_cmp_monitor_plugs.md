---
UID: NS:61883._CMP_MONITOR_PLUGS
title: "_CMP_MONITOR_PLUGS"
author: windows-driver-content
description: This structure is used to monitor plug access. The request allows a driver to monitor all access to local oPCR and iPCR plugs.
old-location: ieee\cmp_monitor_plugs.htm
old-project: IEEE
ms.assetid: D281BCBB-CDC6-442C-9A47-DF07D1BE1B28
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCMP_MONITOR_PLUGS, 61883/CMP_MONITOR_PLUGS, 61883/PCMP_MONITOR_PLUGS, CMP_MONITOR_PLUGS, CMP_MONITOR_PLUGS structure [Buses], IEEE.cmp_monitor_plugs, PCMP_MONITOR_PLUGS, PCMP_MONITOR_PLUGS structure pointer [Buses], _CMP_MONITOR_PLUGS"
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
-	61883.h
api_name:
-	CMP_MONITOR_PLUGS
product:
- Windows
targetos: Windows
req.typenames: CMP_MONITOR_PLUGS, *PCMP_MONITOR_PLUGS
---

# _CMP_MONITOR_PLUGS structure
This structure is used to monitor plug access. The request allows a driver to monitor all access to local oPCR and iPCR plugs.

## Syntax
```
typedef struct _CMP_MONITOR_PLUGS {
  IN ULONG                Flags;
  IN PCMP_MONITOR_ROUTINE pfnNotify;
  IN PVOID                Context;
} CMP_MONITOR_PLUGS, *PCMP_MONITOR_PLUGS;
```

## Members


`Flags`

On input, the caller sets this member to REGISTER_MONITOR_PLUG_NOTIFY to register to monitor all local plug access. This member can also be set to DEREGISTER_MONITOR_PLUG_NOTIFY to stop monitoring local plug access.

`pfnNotify`

On input, aointer to a caller-supplied function to be called by the protocol driver when a local plug is accessed. 

This function uses the following prototype: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef void
(*PCMP_MONITOR_ROUTINE) (
  IN PCMP_MONITOR_INFO  MonitorInfo
  );</pre>
</td>
</tr>
</table></span></div>




#### MonitorInfo

On input, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537050">CMP_MONITOR_INFO</a> structure containing the contents of the plug that was modified.

`Context`

On input, a pointer to a caller-defined context for the function at <b>pfnNotify</b>.

## Remarks
If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 61883.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>