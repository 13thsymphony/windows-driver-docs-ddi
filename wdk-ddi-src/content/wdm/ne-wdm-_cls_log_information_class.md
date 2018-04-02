---
UID: NE:wdm._CLS_LOG_INFORMATION_CLASS
title: "_CLS_LOG_INFORMATION_CLASS"
author: windows-driver-content
description: The CLFS_LOG_INFORMATION_CLASS enumeration indicates the type of information that is requested by a call to ClfsQueryLogFileInformation.
old-location: kernel\clfs_log_information_class.htm
old-project: kernel
ms.assetid: afffe6c3-a6d1-4e43-ba2b-f64269c44ec0
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PCLFS_LOG_INFORMATION_CLASS, *PCLS_LOG_INFORMATION_CLASS, CLFS_LOG_INFORMATION_CLASS, CLFS_LOG_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], CLS_LOG_INFORMATION_CLASS, CLS_LOG_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], ClfsLogBasicInformation, ClfsLogBasicInformationPhysical, ClfsLogPhysicalLsnInformation, ClfsLogPhysicalNameInformation, ClfsLogStreamIdentifierInformation, ClfsLogSystemMarkingInformation, PCLFS_LOG_INFORMATION_CLASS, PCLFS_LOG_INFORMATION_CLASS enumeration pointer [Kernel-Mode Driver Architecture], PCLS_LOG_INFORMATION_CLASS, PCLS_LOG_INFORMATION_CLASS enumeration pointer [Kernel-Mode Driver Architecture], PPCLFS_LOG_INFORMATION_CLASS, PPCLFS_LOG_INFORMATION_CLASS enumeration pointer [Kernel-Mode Driver Architecture], PPCLS_LOG_INFORMATION_CLASS, PPCLS_LOG_INFORMATION_CLASS enumeration pointer [Kernel-Mode Driver Architecture], _CLS_LOG_INFORMATION_CLASS, kernel.clfs_log_information_class, sysenum_b63b4055-ea69-4955-8684-b42b148a3b7c.xml, wdm/CLFS_LOG_INFORMATION_CLASS, wdm/CLS_LOG_INFORMATION_CLASS, wdm/ClfsLogBasicInformation, wdm/ClfsLogBasicInformationPhysical, wdm/ClfsLogPhysicalLsnInformation, wdm/ClfsLogPhysicalNameInformation, wdm/ClfsLogStreamIdentifierInformation, wdm/ClfsLogSystemMarkingInformation, wdm/PCLFS_LOG_INFORMATION_CLASS, wdm/PCLS_LOG_INFORMATION_CLASS, wdm/PPCLFS_LOG_INFORMATION_CLASS, wdm/PPCLS_LOG_INFORMATION_CLASS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	CLS_LOG_INFORMATION_CLASS
product:
- Windows
targetos: Windows
req.typenames: CLS_LOG_INFORMATION_CLASS, *PCLS_LOG_INFORMATION_CLASS, PPCLS_LOG_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# _CLS_LOG_INFORMATION_CLASS Enumeration
The <b>CLFS_LOG_INFORMATION_CLASS</b> enumeration indicates the type of information that is requested by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541679">ClfsQueryLogFileInformation</a>.

## Syntax
```
typedef enum _CLS_LOG_INFORMATION_CLASS {
  ClfsLogBasicInformation             ,
  ClfsLogBasicInformationPhysical     ,
  ClfsLogPhysicalNameInformation      ,
  ClfsLogStreamIdentifierInformation  ,
  ClfsLogSystemMarkingInformation     ,
  ClfsLogPhysicalLsnInformation
} *PCLS_LOG_INFORMATION_CLASS, PPCLS_LOG_INFORMATION_CLASS, CLS_LOG_INFORMATION_CLASS;
```

## Constants

<table>
            
                <tr>
                    <td>ClfsLogBasicInformation</td>
                    <td>Indicates that the request is for basic information about a CLFS stream and its underlying physical log. The information is returned in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541790">CLFS_INFORMATION</a> structure. Most of the structure members contain information about the underlying physical log, but some members contain information that is specific to the stream.</td>
                </tr>
            
                <tr>
                    <td>ClfsLogBasicInformationPhysical</td>
                    <td>Indicates that the request is for basic information about the physical log that underlies a CLFS stream. The information is returned in a <b>CLFS_INFORMATION</b> structure. All of the structure members contain information about the underlying physical log.</td>
                </tr>
            
                <tr>
                    <td>ClfsLogPhysicalNameInformation</td>
                    <td>Indicates that the request is for information about the name of a physical CLFS log. The information is returned in a <b>CLFS_LOG_NAME_INFORMATION</b> structure.</td>
                </tr>
            
                <tr>
                    <td>ClfsLogStreamIdentifierInformation</td>
                    <td>Indicates that the request is for a CLFS stream identifier. The information is returned in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541869">CLFS_STREAM_ID_INFORMATION</a> structure.</td>
                </tr>
            
                <tr>
                    <td>ClfsLogSystemMarkingInformation</td>
                    <td>Count of system marking references. This enumeration constant is supported only in Windows Vista and later versions of Windows.</td>
                </tr>
            
                <tr>
                    <td>ClfsLogPhysicalLsnInformation</td>
                    <td>Maps virtual LSNs to physical LSNs; only valid for physical logs. This enumeration constant is supported only in Windows Vista and later versions of Windows.</td>
                </tr>
</table>

## Remarks

The <i>eInformationClass</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541679">ClfsQueryLogFileInformation</a> function is a value from the <b>CLFS_LOG_INFORMATION_CLASS</b> enumeration.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541679">ClfsQueryLogFileInformation</a>