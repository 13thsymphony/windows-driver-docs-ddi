---
UID : NS:61883._UNIT_DIAG_LEVEL
title : _UNIT_DIAG_LEVEL
author : windows-driver-content
description : The UNIT_DDI_VERSION structure is used in conjunction with the Av61883_GetUnitInfo request to retrieve the current diag level
old-location : ieee\unit_diag_level.htm
old-project : IEEE
ms.assetid : 2759486f-7eaa-4af4-b9a9-2e44354f411b
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _UNIT_DIAG_LEVEL, *PUNIT_DIAG_LEVEL, UNIT_DIAG_LEVEL
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : 61883.h
req.include-header : 61883.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : UNIT_DIAG_LEVEL
req.alt-loc : 61883.h
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
req.typenames : "*PUNIT_DIAG_LEVEL, UNIT_DIAG_LEVEL"
---

# _UNIT_DIAG_LEVEL structure
The UNIT_DDI_VERSION structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a> request to retrieve the current diag level

## Syntax
````
typedef struct _UNIT_DIAG_LEVEL {
  ULONG DiagLevel;
} UNIT_DIAG_LEVEL, *PUNIT_DIAG_LEVEL;
````

## Members

        
            `DiagLevel`

            The bitmask representing the diaglevel. Possible settings are:


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | 61883.h (include 61883.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20UNIT_DIAG_LEVEL structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>