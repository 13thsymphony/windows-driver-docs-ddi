---
UID: NS.NTDDSTOR._STORAGE_LB_PROVISIONING_MAP_RESOURCES
title: _STORAGE_LB_PROVISIONING_MAP_RESOURCES
author: windows-driver-content
description: The STORAGE_LB_PROVISIONING_MAP_RESOURCES structure contains, when valid, the count of available and used bytes mapped to a storage device. This structure is returned from an IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES request.
old-location: storage\storage_lb_provisioning_map_resources.htm
old-project: storage
ms.assetid: 6F7DE233-D002-4927-80FC-307A3A33653A
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _STORAGE_LB_PROVISIONING_MAP_RESOURCES, STORAGE_LB_PROVISIONING_MAP_RESOURCES, PSTORAGE_LB_PROVISIONING_MAP_RESOURCES, *PSTORAGE_LB_PROVISIONING_MAP_RESOURCES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h, Scsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_LB_PROVISIONING_MAP_RESOURCES
req.alt-loc: Ntddstor.h
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

# _STORAGE_LB_PROVISIONING_MAP_RESOURCES structure



## -description
The <b>STORAGE_LB_PROVISIONING_MAP_RESOURCES</b> structure contains, when valid, the count of available and used bytes mapped to a storage device. This structure is returned from an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_lb_provisioning_map_resources.md">IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES</a> request.



## -syntax

````
typedef struct _STORAGE_LB_PROVISIONING_MAP_RESOURCES {
  ULONG     Size;
  ULONG     Version;
  UCHAR     AvailableMappingResourcesValid  :1;
  UCHAR     UsedMappingResourcesValid  :1;
  UCHAR     Reserved0  :6;
  UCHAR     Reserved1[3];
  UCHAR     AvailableMappingResourcesScope  :2;
  UCHAR     UsedMappingResourcesScope  :2;
  UCHAR     Reserved2  :4;
  UCHAR     Reserved3[3];
  ULONGLONG AvailableMappingResources;
  ULONGLONG UsedMappingResources;
} STORAGE_LB_PROVISIONING_MAP_RESOURCES, *PSTORAGE_LB_PROVISIONING_MAP_RESOURCES;
````


## -struct-fields

### -field Size

The size of this structure. This is set to <b>sizeof</b>(STORAGE_LB_PROVISIONING_MAP_RESOURCES).


### -field Version

The version of this structure.


### -field AvailableMappingResourcesValid

The validity of the <b>AvailableMappingResources</b> member.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">

### -field 0

</td>
<td width="60%">
<b>AvailableMappingResources</b> is not valid.

</td>
</tr>
<tr>
<td width="40%">

### -field 1

</td>
<td width="60%">
<b>AvailableMappingResources</b> is valid.

</td>
</tr>
</table>
 


### -field UsedMappingResourcesValid

The validity of the <b>UsedMappingResources</b> member.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">

### -field 0

</td>
<td width="60%">
<b>UsedMappingResources</b> is not valid.

</td>
</tr>
<tr>
<td width="40%">

### -field 1

</td>
<td width="60%">
<b>UsedMappingResources</b> is valid.

</td>
</tr>
</table>
 


### -field Reserved0

Reserved.


### -field Reserved1

Reserved.


### -field AvailableMappingResourcesScope

Resources scope available to a LUN or a LUN pool.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field LOG_PAGE_LBP_RESOURCE_SCOPE_NOT_REPORTED
### -field 0

</td>
<td width="60%">
Mapping resources are not reported.

</td>
</tr>
<tr>

### -field LOG_PAGE_LBP_RESOURCE_SCOPE_DEDICATED_TO_LUN
### -field 1

</td>
<td width="60%">
Mapping resources dedicated to a LUN.

</td>
</tr>
<tr>

### -field LOG_PAGE_LBP_RESOURCE_SCOPE_NOT_DEDICATED_TO_LUN
### -field 2

</td>
<td width="60%">
Mapping resources dedicated to a LUN pool.

</td>
</tr>
</table>
 


### -field UsedMappingResourcesScope

Resources scope used by a LUN or LUN pool.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field LOG_PAGE_LBP_RESOURCE_SCOPE_NOT_REPORTED
### -field 0

</td>
<td width="60%">
Mapping resources are not reported.

</td>
</tr>
<tr>

### -field LOG_PAGE_LBP_RESOURCE_SCOPE_DEDICATED_TO_LUN
### -field 1

</td>
<td width="60%">
Mapping resources dedicated to a LUN.

</td>
</tr>
<tr>

### -field LOG_PAGE_LBP_RESOURCE_SCOPE_NOT_DEDICATED_TO_LUN
### -field 2

</td>
<td width="60%">
Mapping resources dedicated to a LUN pool.

</td>
</tr>
</table>
 


### -field Reserved2

Reserved.


### -field Reserved3

Reserved.


### -field AvailableMappingResources

The count, in bytes, of the available mapping resources for a disk.


### -field UsedMappingResources

The count, in bytes, of the used mapping resources for a disk.


## -remarks
As a managed storage element, resource usage for a thinly provisioned LUN is tracked. Resource allocation is logged for the device by the storage subsystem. A storage application can query for this resource usage  information using the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_lb_provisioning_map_resources.md"> IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES</a> request.

Logging of mapped resource counts is dependent on support from the storage device. The <b>AvailableMappingResources</b> and <b>UsedMappingResources</b> members contain resource counts when their respective validity fields are set.

Resource counts are in bytes instead of totals of blocks or slabs.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddstor.h (include Ntddstor.h or Scsi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_lb_provisioning_map_resources.md"> IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_LB_PROVISIONING_MAP_RESOURCES structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

