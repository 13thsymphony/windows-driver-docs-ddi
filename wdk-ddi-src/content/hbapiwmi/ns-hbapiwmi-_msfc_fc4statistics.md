---
UID : NS:hbapiwmi._MSFC_FC4STATISTICS
title : _MSFC_FC4STATISTICS
author : windows-driver-content
description : The MSFC_FC4STATISTICS structure is used in conjunction with the GetFC4Statistics WMI method to report traffic statistics on a port of type Nx_Port for the indicated FC-4 protocol.
old-location : storage\msfc_fc4statistics.htm
old-project : storage
ms.assetid : a46a9aff-9bc9-4328-85b2-90f8f80b2e65
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _MSFC_FC4STATISTICS, *PMSFC_FC4STATISTICS, MSFC_FC4STATISTICS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : hbapiwmi.h
req.include-header : Hbapiwmi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : MSFC_FC4STATISTICS
req.alt-loc : hbapiwmi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PMSFC_FC4STATISTICS, MSFC_FC4STATISTICS"
---

# _MSFC_FC4STATISTICS structure
The MSFC_FC4STATISTICS structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553949">GetFC4Statistics</a> WMI method to report traffic statistics on a port of type Nx_Port for the indicated FC-4 protocol.

## Syntax
````
typedef struct _MSFC_FC4STATISTICS {
  ULONGLONG InputRequests;
  ULONGLONG OutputRequests;
  ULONGLONG ControlRequests;
  ULONGLONG InputMegabytes;
  ULONGLONG OutputMegabytes;
} MSFC_FC4STATISTICS, *PMSFC_FC4STATISTICS;
````

## Members

        
            `ControlRequests`

            Indicates the number of control requests.
        
            `InputMegabytes`

            Indicates the number of megabytes of data that has been input.
        
            `InputRequests`

            Indicates the number of input requests.
        
            `OutputMegabytes`

            Indicates the number of megabytes of data that has been output.
        
            `OutputRequests`

            Indicates the number of output requests.

    ## Remarks
        The statistics counters whose values are reported in the members of this structure are 64-bit signed integers that wrap to zero on exceeding 2**63-1. The statistics counters are not reset during normal operation, so traffic rates may be determined by the difference of counter values derived from two successive calls, with appropriate adjustments to for counter wrap.

If an HBA does not support a specific statistic, it shall return the value of -1 for corresponding counter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553949">GetFC4Statistics</a>
</dt>
<dt>
<a href="..\hbapiwmi\ns-hbapiwmi-_getfc4statistics_in.md">GetFC4Statistics_IN</a>
</dt>
<dt>
<a href="..\hbapiwmi\ns-hbapiwmi-_getfc4statistics_out.md">GetFC4Statistics_OUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSFC_FC4STATISTICS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>