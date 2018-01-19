---
UID : NS:pepfx._PEP_PPM_PERF_SET
title : _PEP_PPM_PERF_SET
author : windows-driver-content
description : The PEP_PPM_PERF_SET structure specifies the new performance level that the operating system is requesting for the processor.
old-location : kernel\pep_ppm_perf_set.htm
old-project : kernel
ms.assetid : BA2495F6-09E8-4AF9-9489-E745B759F999
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _PEP_PPM_PERF_SET, PEP_PPM_PERF_SET, *PPEP_PPM_PERF_SET
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
req.alt-api : PEP_PPM_PERF_SET
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
req.typenames : PEP_PPM_PERF_SET, *PPEP_PPM_PERF_SET
---

# _PEP_PPM_PERF_SET structure
The <b>PEP_PPM_PERF_SET</b> structure specifies the new performance level that the operating system is requesting for the processor.

## Syntax
````
typedef struct _PEP_PPM_PERF_SET {
  ULONG MinimumPerformance;
  ULONG MaximumPerformance;
  ULONG DesiredPerformance;
  ULONG TimeWindow;
  ULONG PerformanceTolerance;
} PEP_PPM_PERF_SET, *PPEP_PPM_PERF_SET;
````

## Members

        
            `DesiredPerformance`

            [in] The new desired performance level in platform-specific units. This member is set to a value in the range <b>MinimumPerformance</b> to <b>MaximumPerformance</b>.
        
            `MaximumPerformance`

            [in] The new maximum performance level in platform-specific units. This member indicates the absolute maximum performance level that the processor can run at.
        
            `MinimumPerformance`

            [in] The new minimum performance level in platform-specific units. This member indicates the absolute minimum performance level that the processor can run at.
        
            `PerformanceTolerance`

            [in] The new performance tolerance in platform-specific units. This member contains the minimum performance level that the platform can deliver and still meet the operating system's performance requirements.
        
            `TimeWindow`

            [in] The width, in milliseconds, of the new time window over which the platform must provide the required average performance. If this time window is nonzero, the instantaneous performance provided by the platform does not need to match the desired performance level, and only needs to fall within the constraints specified by the minimum and maximum performance level.

    ## Remarks
        This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186816">PEP_NOTIFY_PPM_PERF_SET</a> notification. All five members of this structure contain input values that PoFx supplies when this notification is sent to the PEP.

Processor performance levels are specified in platform-specific units. For example, a hardware platform might use a metric such as the processor clock frequency to provide a rough approximation to the amount of processing work  that is being done. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt629132">Platform Performance Thresholds</a>.

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
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186816">PEP_NOTIFY_PPM_PERF_SET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt629132">Platform Performance Thresholds</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_PERF_SET structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>