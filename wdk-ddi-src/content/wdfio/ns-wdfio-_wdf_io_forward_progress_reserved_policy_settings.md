---
UID: NS:wdfio._WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS
title: "_WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS"
author: windows-driver-content
description: The WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS structure contains information about specific actions that the framework can take when it receives an I/O request for your driver, if a low-memory situation exists.
old-location: wdf\wdf_io_forward_progress_reserved_policy_settings.htm
old-project: wdf
ms.assetid: 28ffe82f-79b6-4a00-b4fa-36df5df303a6
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFQueueObjectRef_47fb2461-dada-4f4e-aba8-91759b3092ea.xml, WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS, WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS structure, _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS, kmdf.wdf_io_forward_progress_reserved_policy_settings, wdf.wdf_io_forward_progress_reserved_policy_settings, wdfio/WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfio.h
api_name:
-	WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS
product: Windows
targetos: Windows
req.typenames: WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS
req.product: Windows 10 or later.
---

# _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS structure
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS</b> structure contains information about specific actions that the framework can take when it receives an I/O request for your driver, if a low-memory situation exists.

## Syntax
````
typedef struct _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS {
  union {
    struct {
      PFN_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS EvtIoWdmIrpForForwardProgress;
    } ExaminePolicy;
  } Policy;
} WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS;
````

## Members


`Policy`



## Remarks
The <b>WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY_SETTINGS</b> structure is used as a member type in the <a href="..\wdfio\ns-wdfio-_wdf_io_queue_forward_progress_policy.md">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.9 |
| **Header** | wdfio.h (include Wdf.h) |