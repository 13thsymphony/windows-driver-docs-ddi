---
UID: NF.hbaapi.HBA_GetFC4Statistics
title: HBA_GetFC4Statistics function
author: windows-driver-content
description: The HBA_GetFC4Statistics routine retrieves traffic statistics that a specific FC-4 protocol has collected for the indicated port and local adapter.
old-location: storage\hba_getfc4statistics.htm
old-project: storage
ms.assetid: 9c86c753-dddf-488d-b332-4b79602c454a
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: HBA_GetFC4Statistics
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_GetFC4Statistics
req.alt-loc: Hbaapi.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
---

# HBA_GetFC4Statistics function



## -description
The <b>HBA_GetFC4Statistics</b> routine retrieves traffic statistics that a specific FC-4 protocol has collected for the indicated port and local adapter. 


## -syntax

````
HBA_STATUS HBA_API HBA_GetFC4Statistics(
  _In_  HBA_HANDLE        handle,
  _In_  HBA_WWN           portWWN,
  _In_  HBA_UINT8         FC4type,
  _Out_ HBA_FC4STATISTICS *statistics
);
````


## -parameters

### -param handle [in]

Contains a value returned by the routine <a href="storage.hba_openadapter">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 

### -param portWWN [in]

Contains a 64-bit world-wide name (WWN) that uniquely identifies the local HBA port for which this routine retrieves traffic statistics for a specific FC-4 protocol. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.

### -param FC4type [in]

Contains a value that indicates the type FC-4 protocol. For an explanation of FC4 types and the values that can be assigned to this parameter, see the T11 committee's <i>Fibre Channel Generic Services - 4 </i>specification. 

### -param statistics [out]

Pointer to a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fc4statistics.md">HBA_FC4Statistics</a> that contains statistics for the specified port and FC-4 protocol. 

## -returns
The <b>HBA_GetFC4Statistics</b> routine returns a value of type <a href="storage.hba_status">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetFC4Statistics</b> returns one of the following qualifiers.
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>Returned if the adapter does not contain a port with the name <i>HbaPortWWN</i>. 
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>Returned if the adapter does not support the specified FC-4 protocol. 
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the retrieval of the port attributes.

 

## -remarks
Statistics counters in <a href="..\hbaapi\ns-hbaapi-hba_fc4statistics.md">HBA_FC4Statistics</a> are 64-bit signed integers that wrap to zero on exceeding 2**63-1. If an HBA does not support a specific statistic, it returns a value with every bit set to 1 for that statistic. For an explanation of how the counter values are determined, see the T11 committee's <i>Fibre Channel Generic Services - 4 </i>specification. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Hbaapi.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>Hbaapi.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hbaapi\ns-hbaapi-hba_fc4statistics.md">HBA_FC4Statistics</a>
</dt>
<dt>
<a href="storage.hba_openadapter">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="storage.hba_status">HBA_STATUS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetFC4Statistics routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
