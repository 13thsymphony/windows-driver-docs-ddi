---
UID : NS:wdm._CLFS_MGMT_CLIENT_REGISTRATION
title : _CLFS_MGMT_CLIENT_REGISTRATION
author : windows-driver-content
description : The CLFS_MGMT_CLIENT_REGISTRATION structure is given to CLFS management by clients who manage their own logs.
old-location : kernel\clfs_mgmt_client_registration.htm
old-project : kernel
ms.assetid : 4f4f7ece-efe4-49f7-a6ce-bc131d1c1968
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _CLFS_MGMT_CLIENT_REGISTRATION, *PCLFS_MGMT_CLIENT_REGISTRATION, CLFS_MGMT_CLIENT_REGISTRATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : CLFS_MGMT_CLIENT_REGISTRATION
req.alt-loc : wdm.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL (see Remarks section)
req.typenames : "*PCLFS_MGMT_CLIENT_REGISTRATION, CLFS_MGMT_CLIENT_REGISTRATION"
req.product : Windows 10 or later.
---

# _CLFS_MGMT_CLIENT_REGISTRATION structure
The <b>CLFS_MGMT_CLIENT_REGISTRATION</b> structure is given to CLFS management by clients who manage their own logs.

## Syntax
````
typedef struct _CLFS_MGMT_CLIENT_REGISTRATION {
  ULONG                                      Version;
  PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK         AdvanceTailCallback;
  PVOID                                      AdvanceTailCallbackData;
  PCLFS_CLIENT_LFF_HANDLER_COMPLETE_CALLBACK LogGrowthCompleteCallback;
  PVOID                                      LogGrowthCompleteCallbackData;
  PCLFS_CLIENT_LOG_UNPINNED_CALLBACK         LogUnpinnedCallback;
  PVOID                                      LogUnpinnedCallbackData;
} CLFS_MGMT_CLIENT_REGISTRATION, *PCLFS_MGMT_CLIENT_REGISTRATION;
````

## Members

        
            `AdvanceTailCallback`

            A pointer to the log's <a href="..\wdm\nc-wdm-pclfs_client_advance_tail_callback.md">ClfsAdvanceTailCallback</a> function.
        
            `AdvanceTailCallbackData`

            A pointer to user-defined data that will be supplied to the <i>ClfsAdvanceTailCallback</i> function when the function is invoked.
        
            `LogGrowthCompleteCallback`

            A pointer to the log's <a href="..\wdm\nc-wdm-pclfs_client_lff_handler_complete_callback.md">ClfsLogGrowthCompleteCallback</a> function.
        
            `LogGrowthCompleteCallbackData`

            A pointer to user-defined data that will be supplied to the <i>ClfsLogGrowthCompleteCallback</i> function when the function is invoked.
        
            `LogUnpinnedCallback`

            A pointer to the log's <a href="..\wdm\nc-wdm-pclfs_client_log_unpinned_callback.md">ClfsLogUnpinnedCallback</a> function.
        
            `LogUnpinnedCallbackData`

            A pointer to user-defined data that will be supplied to the <i>ClfsLogUnpinnedCallback</i> function when the function is invoked.
        
            `Version`

            The version of the <b>CLFS_MGMT_CLIENT_REGISTRATION</b> structure. Set this to <b>CLFS_MGMT_CLIENT_REGISTRATION_VERSION</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h) |

    ## See Also

        <dl>
<dt>
<a href="..\wdm\nc-wdm-pclfs_client_advance_tail_callback.md">ClfsAdvanceTailCallback</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pclfs_client_lff_handler_complete_callback.md">ClfsLogGrowthCompleteCallback</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pclfs_client_log_unpinned_callback.md">ClfsLogUnpinnedCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CLFS_MGMT_CLIENT_REGISTRATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>