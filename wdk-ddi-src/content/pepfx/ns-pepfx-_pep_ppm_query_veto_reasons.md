---
UID : NS:pepfx._PEP_PPM_QUERY_VETO_REASONS
title : _PEP_PPM_QUERY_VETO_REASONS
author : windows-driver-content
description : The PEP_PPM_QUERY_VETO_REASONS structure specifies the total number of veto reasons that the PEP uses in calls to the ProcessorIdleVeto and PlatformIdleVeto routines.
old-location : kernel\pep_ppm_query_veto_reasons.htm
old-project : kernel
ms.assetid : 59D0D139-00E4-4EEE-A326-0A2979B2085B
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _PEP_PPM_QUERY_VETO_REASONS, *PPEP_PPM_QUERY_VETO_REASONS, PEP_PPM_QUERY_VETO_REASONS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : pepfx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 10.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PEP_PPM_QUERY_VETO_REASONS
req.alt-loc : pepfx.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PPEP_PPM_QUERY_VETO_REASONS, PEP_PPM_QUERY_VETO_REASONS"
---

# _PEP_PPM_QUERY_VETO_REASONS structure
The <b>PEP_PPM_QUERY_VETO_REASONS</b> structure specifies the total number of veto reasons that the PEP uses in calls to the <a href="..\pepfx\nc-pepfx-pofxcallbackprocessoridleveto.md">ProcessorIdleVeto</a> and <a href="..\pepfx\nc-pepfx-pofxcallbackplatformidleveto.md">PlatformIdleVeto</a> routines.

## Syntax
````
typedef struct _PEP_PPM_QUERY_VETO_REASONS {
  ULONG VetoReasonCount;
} PEP_PPM_QUERY_VETO_REASONS, *PPEP_PPM_QUERY_VETO_REASONS;
````

## Members

        
            `VetoReasonCount`

            [out] The number of veto codes used by the PEP.

    ## Remarks
        This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASONS</a> notification. The <b>VetoReasonCount</b> member contains an output value that the PEP writes to this member in response to the notification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pepfx.h |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASONS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_QUERY_VETO_REASONS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>