---
UID: NS:wdm._PCW_CALLBACK_INFORMATION
title: "_PCW_CALLBACK_INFORMATION"
author: windows-driver-content
description: The PCW_CALLBACK_INFORMATION union supplies details about the notification to send. A provider passes a pointer to this union as a parameter to the PcwCallback function.
old-location: devtest\pcw_callback_information.htm
old-project: devtest
ms.assetid: cc1882a9-eba7-494c-9047-5c97b1e3c19b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PPCW_CALLBACK_INFORMATION, PCW_CALLBACK_INFORMATION, PCW_CALLBACK_INFORMATION union [Driver Development Tools], PPCW_CALLBACK_INFORMATION, PPCW_CALLBACK_INFORMATION union pointer [Driver Development Tools], _PCW_CALLBACK_INFORMATION, devtest.pcw_callback_information, km_pcw_d44ee92a-c8a0-4da9-8739-cf5443ee2d85.xml, wdm/PCW_CALLBACK_INFORMATION, wdm/PPCW_CALLBACK_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	PCW_CALLBACK_INFORMATION
product: Windows
targetos: Windows
req.typenames: PCW_CALLBACK_INFORMATION, *PPCW_CALLBACK_INFORMATION
req.product: Windows 10 or later.
---

# _PCW_CALLBACK_INFORMATION structure
The <b>PCW_CALLBACK_INFORMATION</b> union supplies details about the notification to send. A provider passes a pointer to this union as a parameter to the <a href="https://msdn.microsoft.com/5058fc17-1016-45bc-a6ea-5e2458824e7b">PcwCallback</a> function.

## Syntax
```
typedef struct _PCW_CALLBACK_INFORMATION {
  PCW_COUNTER_INFORMATION AddCounter;
  PCW_COUNTER_INFORMATION RemoveCounter;
  PCW_MASK_INFORMATION    EnumerateInstances;
  PCW_MASK_INFORMATION    CollectData;
} *PPCW_CALLBACK_INFORMATION, PCW_CALLBACK_INFORMATION;
```

## Members


`AddCounter`

The PCW_COUNTER_INFORMATION structure that identifies the counter being added.

`RemoveCounter`

The PCW_COUNTER_INFORMATION structure that identifies the counter being removed.

`EnumerateInstances`

The PCW_MASK_INFORMATION structure that identifies the instances of the counter set.

`CollectData`

The PCW_MASK_INFORMATION structure that identifies the instance of the counter set and its buffer.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550341">PCW_COUNTER_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550346">PCW_MASK_INFORMATION</a>