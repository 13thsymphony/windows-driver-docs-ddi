---
UID: NE.ntddcdrm._CDROM_PERFORMANCE_EXCEPTION_TYPE
title: _CDROM_PERFORMANCE_EXCEPTION_TYPE
author: windows-driver-content
description: The CDROM_PERFORMANCE_EXCEPTION_TYPE enumeration defines the exceptional conditions for performance data.
old-location: storage\cdrom_performance_exception_type.htm
old-project: storage
ms.assetid: 4AD156F8-911F-4D70-8B0E-8BB0D0747470
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _CDROM_PERFORMANCE_EXCEPTION_TYPE, CDROM_PERFORMANCE_EXCEPTION_TYPE, *PCDROM_PERFORMANCE_EXCEPTION_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CDROM_PERFORMANCE_EXCEPTION_TYPE
req.alt-loc: Ntddcdrm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# _CDROM_PERFORMANCE_EXCEPTION_TYPE enumeration



## -description
The <b>CDROM_PERFORMANCE_EXCEPTION_TYPE</b> enumeration defines the exceptional conditions for performance data. It is a member of the <a href="storage.cdrom_performance_request">CDROM_PERFORMANCE_REQUEST</a> structure, which is used as an input parameter to the  <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request. 



## -syntax

````
typedef enum _CDROM_PERFORMANCE_EXCEPTION_TYPE { 
  CdromNominalPerformance             = 1,
  CdromEntirePerformanceList          = 2,
     CdromPerformanceExceptionsOnly   = 3
} CDROM_PERFORMANCE_EXCEPTION_TYPE, *PCDROM_PERFORMANCE_EXCEPTION_TYPE;
````


## -enum-fields

### -field CdromNominalPerformance

Requests nominal performance parameters.


### -field CdromEntirePerformanceList

Requests the entire performance list, as qualified by the <b>StartingLba</b> field of the <a href="storage.cdrom_performance_request">CDROM_PERFORMANCE_REQUEST</a> structure.


### -field    CdromPerformanceExceptionsOnly 

Requests only performance exceptions that cause the performance to fall outside the nominal.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddcdrm.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.cdrom_performance_request">CDROM_PERFORMANCE_REQUEST</a>
</dt>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_PERFORMANCE_EXCEPTION_TYPE enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

