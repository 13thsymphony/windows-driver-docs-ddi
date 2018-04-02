---
UID: NS:wdm._PCW_REGISTRATION_INFORMATION
title: "_PCW_REGISTRATION_INFORMATION"
author: windows-driver-content
description: The PCW_REGISTRATION_INFORMATION structure supplies details about the provider and the counter set.
old-location: devtest\pcw_registration_information.htm
old-project: devtest
ms.assetid: f5305351-10b4-47e6-a8b6-e1a91c605ca9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PPCW_REGISTRATION_INFORMATION, PCW_REGISTRATION_INFORMATION, PCW_REGISTRATION_INFORMATION structure [Driver Development Tools], PPCW_REGISTRATION_INFORMATION, PPCW_REGISTRATION_INFORMATION structure pointer [Driver Development Tools], _PCW_REGISTRATION_INFORMATION, devtest.pcw_registration_information, km_pcw_a740182f-4844-4a98-9493-522087a3d27c.xml, wdm/PCW_REGISTRATION_INFORMATION, wdm/PPCW_REGISTRATION_INFORMATION"
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
-	PCW_REGISTRATION_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PCW_REGISTRATION_INFORMATION, *PPCW_REGISTRATION_INFORMATION
req.product: Windows 10 or later.
---

# _PCW_REGISTRATION_INFORMATION structure
The PCW_REGISTRATION_INFORMATION structure supplies details about the provider and the counter set.

## Syntax
```
typedef struct _PCW_REGISTRATION_INFORMATION {
  ULONG                   Version;
  PCUNICODE_STRING        Name;
  ULONG                   CounterCount;
  PPCW_COUNTER_DESCRIPTOR Counters;
  PPCW_CALLBACK           Callback;
  PVOID                   CallbackContext;
} PCW_REGISTRATION_INFORMATION, *PPCW_REGISTRATION_INFORMATION;
```

## Members


`Version`

The numeric value that specifies the version of Performance Counters for Windows (PCW) that the provider supports.

`Name`

A pointer to the string that contains the name of the counter set to register.

`CounterCount`

The number of counters that are exposed by this registration.

`Counters`

A pointer to the array that describes the counters.

`Callback`

A pointer to the optional <a href="https://msdn.microsoft.com/5058fc17-1016-45bc-a6ea-5e2458824e7b">PcwCallback</a> function that notifies the provider about events related to this counter set.

`CallbackContext`

A pointer to the callback context.

## Remarks
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff550323">PcwRegister</a> function takes, as a parameter, a pointer to this structure to serve as the registration handle.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550338">PCW_COUNTER_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/5058fc17-1016-45bc-a6ea-5e2458824e7b">PcwCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550323">PcwRegister</a>