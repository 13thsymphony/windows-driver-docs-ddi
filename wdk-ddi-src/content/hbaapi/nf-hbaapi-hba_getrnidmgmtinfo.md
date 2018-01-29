---
UID : NF:hbaapi.HBA_GetRNIDMgmtInfo
title : HBA_GetRNIDMgmtInfo function
author : windows-driver-content
description : The HBA_GetRNIDMgmtInfo routine queries the HBA for request node identification data (RNID) management information.
old-location : storage\hba_getrnidmgmtinfo.htm
old-project : storage
ms.assetid : 8018d52d-4454-4826-933f-a34a70243547
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : fibreHBA_rtns_73ba5195-497c-4105-9b4c-eccd637962b9.xml, HBA_GetRNIDMgmtInfo routine [Storage Devices], HBA_GetRNIDMgmtInfo, hbaapi/HBA_GetRNIDMgmtInfo, storage.hba_getrnidmgmtinfo
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : hbaapi.h
req.include-header : Hbaapi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Hbaapi.lib
req.dll : Hbaapi.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : HBA_WWNTYPE
---


# HBA_GetRNIDMgmtInfo function
The <b>HBA_GetRNIDMgmtInfo</b> routine queries the HBA for request node identification data (RNID) management information.

## Syntax

````
HBA_STATUS HBA_API HBA_GetRNIDMgmtInfo(
  _In_  HBA_HANDLE   HbaHandle,
  _Out_ HBA_MGMTINFO *HbaMgmtInfo
);
````

## Parameters

`Handle`

TBD

`pInfo`

TBD


## Return Value

The <b>HBA_GetRNIDMgmtInfo</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetRNIDMgmtInfo</b> returns one of the following qualifiers.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the management information was successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the retrieval of the management information. 

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>

<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>

<a href="..\hbaapi\ns-hbaapi-hba_mgmtinfo.md">HBA_MgmtInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetRNIDMgmtInfo routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>