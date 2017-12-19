---
UID: NS.WDFIO._WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS
title: _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS
author: windows-driver-content
description: The WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS structure contains information about specific actions that the framework can take when it receives an I/O request for your driver, if a low-memory situation exists.
old-location: wdf\wdf_io_forward_progress_reserved_policy_settings.htm
old-project: wdf
ms.assetid: 28ffe82f-79b6-4a00-b4fa-36df5df303a6
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS, WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.alt-api: WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS
req.alt-loc: wdfio.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any IRQL.
req.product: Windows 10 or later.
---

# _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS structure



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS</b> structure contains information about specific actions that the framework can take when it receives an I/O request for your driver, if a low-memory situation exists.



## -syntax

````
typedef struct _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS {
  union {
    struct {
      PFN_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS EvtIoWdmIrpForForwardProgress;
    } ExaminePolicy;
  } Policy;
} WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS;
````


## -struct-fields

### -field Policy


### -field ExaminePolicy


### -field EvtIoWdmIrpForForwardProgress

A pointer to the driver's queue-specific <a href="..\wdfio\nc-wdfio-evt_wdf_io_wdm_irp_for_forward_progress.md">EvtIoWdmIrpForForwardProgress</a> callback function.

</dd>
</dl>
</dd>
</dl>

## -remarks
The <b>WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS</b> structure is used as a member type in the <a href="wdf.wdf_io_queue_forward_progress_policy">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.9

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfio.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>