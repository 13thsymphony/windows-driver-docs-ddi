---
UID: NS:scsiwmi._SCSIWMILIB_CONTEXT
title: "_SCSIWMILIB_CONTEXT"
author: windows-driver-content
description: A SCSI_WMILIB_CONTEXT structure provides registration information for a miniport driver's data and event blocks and defines entry points for the miniport driver's HwScsiWmiXxx callback routines.
old-location: storage\scsi_wmilib_context.htm
old-project: storage
ms.assetid: 7886cee8-1142-42e6-8206-84667621ba77
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSCSI_WMILIB_CONTEXT, PSCSI_WMILIB_CONTEXT, PSCSI_WMILIB_CONTEXT structure pointer [Storage Devices], SCSI_WMILIB_CONTEXT, SCSI_WMILIB_CONTEXT structure [Storage Devices], _SCSIWMILIB_CONTEXT, scsiwmi/PSCSI_WMILIB_CONTEXT, scsiwmi/SCSI_WMILIB_CONTEXT, storage.scsi_wmilib_context, structs-scsibus_725dbb64-2d39-493d-b1bf-e056ca31244f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	scsiwmi.h
api_name:
-	SCSI_WMILIB_CONTEXT
product: Windows
targetos: Windows
req.typenames: SCSI_WMILIB_CONTEXT, *PSCSI_WMILIB_CONTEXT
req.product: Windows 10 or later.
---

# _SCSIWMILIB_CONTEXT structure
A SCSI_WMILIB_CONTEXT structure provides registration information for a miniport driver's data and event blocks and defines entry points for the miniport driver's <b>HwScsiWmi</b><b><i>Xxx</i></b> callback routines. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
````
typedef struct _SCSIWMILIB_CONTEXT {
  ULONG                     GuidCount;
  PSCSIWMIGUIDREGINFO       GuidList;
  PSCSIWMI_QUERY_REGINFO    QueryWmiRegInfo;
  PSCSIWMI_QUERY_DATABLOCK  QueryWmiDataBlock;
  PSCSIWMI_SET_DATABLOCK    SetWmiDataBlock;
  PSCSIWMI_SET_DATAITEM     SetWmiDataItem;
  PSCSIWMI_EXECUTE_METHOD   ExecuteWmiMethod;
  PSCSIWMI_FUNCTION_CONTROL WmiFunctionControl;
} SCSI_WMILIB_CONTEXT, *PSCSI_WMILIB_CONTEXT;
````

## Members


`GuidCount`

Specifies the number of structures in the SCSIWMIGUIDREGINFO array at <b>GuidList</b>.

`GuidList`

Points to an array of <b>GuidCount</b> SCSIWMIGUIDREGINFO structures that contain registration information for each block.

`QueryWmiRegInfo`

Points to the driver's <a href="..\scsiwmi\nc-scsiwmi-pscsiwmi_query_reginfo.md">HwScsiWmiQueryReginfo</a> routine, which is a required entry point for miniport drivers that support WMI.

`QueryWmiDataBlock`

Points to the driver's <a href="..\scsiwmi\nc-scsiwmi-pscsiwmi_query_datablock.md">HwScsiWmiQueryDataBlock</a> routine, which is a required entry point for miniport drivers that support WMI.

`SetWmiDataBlock`

Points to the driver's <a href="..\scsiwmi\nc-scsiwmi-pscsiwmi_set_datablock.md">HwScsiWmiSetDataBlock</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>

`SetWmiDataItem`

Points to the driver's <a href="..\scsiwmi\nc-scsiwmi-pscsiwmi_set_dataitem.md">HwScsiWmiSetDataItem</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>.

`ExecuteWmiMethod`

Points to the driver's <a href="..\scsiwmi\nc-scsiwmi-pscsiwmi_execute_method.md">HwScsiWmiExecuteMethod</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>

`WmiFunctionControl`

Points to the driver's <a href="..\scsiwmi\nc-scsiwmi-pscsiwmi_function_control.md">HwScsiWmiFunctionControl</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>.

## Remarks
A SCSI miniport driver that supports WMI stores an initialized SCSI_WMILIB_CONTEXT structure (or a pointer to such a structure) in its device extension. A miniport driver can use the same SCSI_WMILIB_CONTEXT structure for multiple device objects if each device object supplies the same set of data blocks. 

When the miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a> with request parameters, including a pointer to an initialized SCSI_WMILIB_CONTEXT structure. <b>ScsiPortWmiDispatchFunction</b> handles the request by calling the miniport driver's appropriate HwScsiWmiXxx routine.

If the miniport driver does not implement an optional HwScsiWmiXxx routine, the port driver returns an appropriate status to the caller.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | scsiwmi.h (include Scsiwmi.h) |

## See Also

<a href="..\scsiwmi\nc-scsiwmi-pscsiwmi_function_control.md">HwScsiWmiFunctionControl</a>



<a href="..\scsiwmi\nc-scsiwmi-pscsiwmi_query_reginfo.md">HwScsiWmiQueryReginfo</a>



<a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>



<a href="..\scsiwmi\ns-scsiwmi-scsiwmiguidreginfo.md">SCSIWMIGUIDREGINFO</a>



<a href="..\scsiwmi\nc-scsiwmi-pscsiwmi_set_datablock.md">HwScsiWmiSetDataBlock</a>



<a href="..\scsiwmi\nc-scsiwmi-pscsiwmi_query_datablock.md">HwScsiWmiQueryDataBlock</a>



<a href="..\scsiwmi\nc-scsiwmi-pscsiwmi_execute_method.md">HwScsiWmiExecuteMethod</a>



<a href="..\scsiwmi\nc-scsiwmi-pscsiwmi_set_dataitem.md">HwScsiWmiSetDataItem</a>