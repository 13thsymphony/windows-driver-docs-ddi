---
UID: NS:wdm._CLFS_MGMT_CLIENT_REGISTRATION
title: "_CLFS_MGMT_CLIENT_REGISTRATION"
author: windows-driver-content
description: The CLFS_MGMT_CLIENT_REGISTRATION structure is given to CLFS management by clients who manage their own logs.
old-location: kernel\clfs_mgmt_client_registration.htm
old-project: kernel
ms.assetid: 4f4f7ece-efe4-49f7-a6ce-bc131d1c1968
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PCLFS_MGMT_CLIENT_REGISTRATION, CLFS_MGMT_CLIENT_REGISTRATION, CLFS_MGMT_CLIENT_REGISTRATION structure [Kernel-Mode Driver Architecture], PCLFS_MGMT_CLIENT_REGISTRATION, PCLFS_MGMT_CLIENT_REGISTRATION structure pointer [Kernel-Mode Driver Architecture], _CLFS_MGMT_CLIENT_REGISTRATION, kernel.clfs_mgmt_client_registration, kstruct_a_b4089ae7-0e80-4da0-b062-cda3d5aa65f4.xml, wdm/CLFS_MGMT_CLIENT_REGISTRATION, wdm/PCLFS_MGMT_CLIENT_REGISTRATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	CLFS_MGMT_CLIENT_REGISTRATION
product: Windows
targetos: Windows
req.typenames: CLFS_MGMT_CLIENT_REGISTRATION, *PCLFS_MGMT_CLIENT_REGISTRATION
req.product: Windows 10 or later.
---

# _CLFS_MGMT_CLIENT_REGISTRATION structure
The <b>CLFS_MGMT_CLIENT_REGISTRATION</b> structure is given to CLFS management by clients who manage their own logs.

## Syntax
```
typedef struct _CLFS_MGMT_CLIENT_REGISTRATION {
  ULONG                                      Version;
  PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK         AdvanceTailCallback;
  PVOID                                      AdvanceTailCallbackData;
  PCLFS_CLIENT_LFF_HANDLER_COMPLETE_CALLBACK LogGrowthCompleteCallback;
  PVOID                                      LogGrowthCompleteCallbackData;
  PCLFS_CLIENT_LOG_UNPINNED_CALLBACK         LogUnpinnedCallback;
  PVOID                                      LogUnpinnedCallbackData;
} *PCLFS_MGMT_CLIENT_REGISTRATION, CLFS_MGMT_CLIENT_REGISTRATION;
```

## Members


`Version`

The version of the <b>CLFS_MGMT_CLIENT_REGISTRATION</b> structure. Set this to <b>CLFS_MGMT_CLIENT_REGISTRATION_VERSION</b>.

`AdvanceTailCallback`

A pointer to the log's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540776">ClfsAdvanceTailCallback</a> function.

`AdvanceTailCallbackData`

A pointer to user-defined data that will be supplied to the <i>ClfsAdvanceTailCallback</i> function when the function is invoked.

`LogGrowthCompleteCallback`

A pointer to the log's <a href="https://msdn.microsoft.com/library/windows/hardware/ff541562">ClfsLogGrowthCompleteCallback</a> function.

`LogGrowthCompleteCallbackData`

A pointer to user-defined data that will be supplied to the <i>ClfsLogGrowthCompleteCallback</i> function when the function is invoked.

`LogUnpinnedCallback`

A pointer to the log's <a href="https://msdn.microsoft.com/library/windows/hardware/ff541565">ClfsLogUnpinnedCallback</a> function.

`LogUnpinnedCallbackData`

A pointer to user-defined data that will be supplied to the <i>ClfsLogUnpinnedCallback</i> function when the function is invoked.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540776">ClfsAdvanceTailCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541562">ClfsLogGrowthCompleteCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541565">ClfsLogUnpinnedCallback</a>