---
UID: NS.GNSSDRIVER.PGNSS_AGNSS_INJECT
title: PGNSS_AGNSS_INJECT
author: windows-driver-content
description: This structure defines the parameters for AGNSS injection.
old-location: sensors\gnss_agnss_inject.htm
old-project: sensors
ms.assetid: B81F5D71-9928-412C-8199-787E71CE2638
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PGNSS_AGNSS_INJECT, *PGNSS_AGNSS_INJECT, GNSS_AGNSS_INJECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_AGNSS_INJECT
req.alt-loc: gnssdriver.h
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

# PGNSS_AGNSS_INJECT structure



## -description
This structure defines the parameters for AGNSS injection.



## -syntax

````
typedef struct {
  ULONG                   Size;
  ULONG                   Version;
  GNSS_AGNSS_REQUEST_TYPE InjectionType;
  NTSTATUS                InjectionStatus;
  ULONG                   InjectionDataSize;
  BYTE                    Unused[512];
  union {
    GNSS_AGNSS_INJECTTIME     Time;
    GNSS_AGNSS_INJECTPOSITION Position;
    GNSS_AGNSS_INJECTBLOB     BlobData;
  };
} GNSS_AGNSS_INJECT, *PGNSS_AGNSS_INJECT;
````


## -struct-fields

### -field Size

Structure size.


### -field Version

Version number.


### -field InjectionType

Indicates the specific type of AGNSS injection. 

Depending on the type, the driver must access the specific data element of the structure. For example, if the type is GNSS_AGNSS_PositionInjection, use the Position element.


### -field InjectionStatus

Indicates whether any error was encountered in gathering the needed injection data. 

The driver must ignore the injection if this field does not indicate success.


### -field InjectionDataSize

Size of the injection data.


### -field Unused[512]

Padding buffer.


### -field Time


<a href="sensors.gnss_agnss_injecttime">GNSS_AGNSS_INJECTTIME</a> contains the format for AGNSS time injection.


### -field Position


<a href="sensors.gnss_agnss_injectposition">GNSS_AGNSS_INJECTPOSITION</a> contains  the format for AGNSS position injection.


### -field BlobData


<a href="sensors.gnss_agnss_injectblob">GNSS_AGNSS_INJECTBLOB</a>  contains the format for AGNSS extended ephemeris injection.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>