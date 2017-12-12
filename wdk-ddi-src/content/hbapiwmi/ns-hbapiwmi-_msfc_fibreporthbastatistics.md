---
UID: NS.HBAPIWMI._MSFC_FIBREPORTHBASTATISTICS
title: _MSFC_FibrePortHBAStatistics
author: windows-driver-content
description: The MSFC_FibrePortHBAStatistics structure is used by an HBA miniport driver that is a WMI provider to report statistics related to a fibre channel port.
old-location: storage\msfc_fibreporthbastatistics.htm
old-project: storage
ms.assetid: 8b365e7a-6d52-417f-8c0b-78feac24602f
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _MSFC_FibrePortHBAStatistics, *PMSFC_FibrePortHBAStatistics, MSFC_FibrePortHBAStatistics
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MSFC_FibrePortHBAStatistics
req.alt-loc: hbapiwmi.h
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

# _MSFC_FibrePortHBAStatistics structure



## -description
The MSFC_FibrePortHBAStatistics structure is used by an HBA miniport driver that is a WMI provider to report statistics related to a fibre channel port.



## -syntax

````
typedef struct _MSFC_FibrePortHBAStatistics {
  ULONGLONG              UniquePortId;
  ULONG                  HBAStatus;
  MSFC_HBAPortStatistics Statistics;
} MSFC_FibrePortHBAStatistics, *PMSFC_FibrePortHBAStatistics;
````


## -struct-fields

### -field UniquePortId

Contains a unique identifier for the port. 


### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="storage.hba_status">HBA_STATUS</a>. 


### -field Statistics

Contains a structure of type <a href="storage.msfc_hbaportstatistics">MSFC_HBAPortStatistics</a> with statistical information about the port. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.msfc_fibreporthbastatistics_wmi_class">MSFC_FibrePortHBAStatistics WMI Class</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSFC_FibrePortHBAStatistics structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

