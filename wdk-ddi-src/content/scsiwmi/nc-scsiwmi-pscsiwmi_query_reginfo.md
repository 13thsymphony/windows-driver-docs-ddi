---
UID: NC:scsiwmi.PSCSIWMI_QUERY_REGINFO
title: PSCSIWMI_QUERY_REGINFO
author: windows-driver-content
description: A miniport driver's HwScsiWmiQueryReginfo routine is called to obtain information about the data and event blocks to be registered on behalf of the miniport driver by the SCSI port driver.
old-location: storage\hwscsiwmiqueryreginfo.htm
old-project: storage
ms.assetid: 416f8629-324f-4698-bbe9-699f5d53011e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: RxScavengeFobxsForNetRoot
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HwScsiWmiQueryReginfo
req.alt-loc: scsiwmi.h
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
req.typenames: *PRX_CONTEXT, RX_CONTEXT
req.product: Windows 10 or later.
---

# PSCSIWMI_QUERY_REGINFO callback



## -description
A miniport driver's <b>HwScsiWmiQueryReginfo</b> routine is called to obtain information about the data and event blocks to be registered on behalf of the miniport driver by the SCSI port driver. This routine is required.



## -prototype

````
UCHAR HwScsiWmiQueryReginfo(
  _In_  PVOID                    DeviceContext,
  _In_  PSCSIWMI_REQUEST_CONTEXT RequestContext,
  _Out_ PWCHAR                   *MofResourceName
);
````


## -parameters

### -param DeviceContext [in]

Points to the miniport driver-defined context value passed to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. 


### -param RequestContext [in]

Points to the SCSIWMI_REQUEST_CONTEXT structure that the miniport driver passed to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. 


### -param MofResourceName [out]

Points to a <b>null</b>-terminated Unicode string that indicates the name of the MOF resource attached to the miniport driver's binary image file. This string can be declared as a constant in the miniport driver. If the miniport driver does not have a MOF resource attached, it should set <i>MofResourceName</i> to <b>NULL</b>. 


## -returns
<b>HwScsiWmiQueryReginfo</b> always returns SRB_STATUS_SUCCESS.


## -remarks
When a miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a> with a pointer to an initialized SCSI_WMILIB_CONTEXT structure and <i>MinorFunction</i> set to <b>Srb-&gt;WmiSubFunction</b>. If <i>MinorFunction</i> indicates a request for registration information, the SCSI port driver calls the miniport driver's <b>HwScsiWmiQueryReginfo</b> routine.

The miniport driver provides new or updated registration information about individual blocks, or indicates blocks to remove, in the SCSI_WMILIB_CONTEXT structure it passes to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. The miniport driver's <b>HwScsiWmiQueryReginfo</b> routine supplies a pointer to its MOF resource name.

The miniport driver must not pend or block the SRB. The miniport driver must not call <a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff564657">ScsiPortNotification</a> from its <b>HwScsiWmiQueryReginfo</b> routine.


## -see-also
<dl>
<dt>
<a href="..\scsiwmi\ns-scsiwmi-_scsiwmilib_context.md">SCSI_WMILIB_CONTEXT</a>
</dt>
<dt>
<a href="..\scsiwmi\ns-scsiwmi-scsiwmi_request_context.md">SCSIWMI_REQUEST_CONTEXT</a>
</dt>
<dt>
<a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HwScsiWmiQueryReginfo callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

