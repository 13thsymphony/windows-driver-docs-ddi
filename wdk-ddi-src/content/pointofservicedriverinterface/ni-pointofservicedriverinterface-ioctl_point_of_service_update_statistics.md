---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS
title: IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS
author: windows-driver-content
description: This I/O control function sets the specified statistic to the value in the input buffer.
old-location: pos\ioctl_point_of_service_update_statistics.htm
old-project: pos
ms.assetid: 94c8d49a-5136-49f3-a313-74c032502f1f
ms.author: windowsdriverdev
ms.date: 2/19/2018
ms.keywords: pos.ioctl_point_of_service_update_statistics, IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS control code, IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pointofservicedriverinterface.h
apiname:
-	IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS
product: Windows
targetos: Windows
req.typenames: PosPropertyId
---

# IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS IOCTL
This I/O control function sets the specified statistic to the value in the input buffer.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posstatisticsheader.md">PosStatisticsHeader</a> where <i>PosStatisticsHeader.EntryCount</i> is set to the number of statistics to update. This structure is then followed by a corresponding number of <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posvaluestatisticsentry.md">PosValueStatisticsEntry</a> structures that contain the name of a statistic and the corresponding value to which it will be updated.

### Input Buffer Length
The sizeof(<i>PosStatisticsHeader</i>) + <i>PosStatisticsHeader.EntryCount</i> * sizeof(<i>PosValueStatisticsEntry</i>).

### Output Buffer
Not used with this operation; set to <b>NULL</b>.

### Output Buffer Length
Not used with this operation; set to <b>0</b> (zero).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following list shows common error values:

## Remarks
<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicedriverinterface.h (include Pointofservicedriverinterface.h) |