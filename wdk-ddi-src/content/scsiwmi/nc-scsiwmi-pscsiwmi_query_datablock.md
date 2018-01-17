---
UID: NC:scsiwmi.PSCSIWMI_QUERY_DATABLOCK
title: PSCSIWMI_QUERY_DATABLOCK
author: windows-driver-content
description: A miniport driver's HwScsiWmiQueryDataBlock routine is called to obtain either a single instance or all instances of a data block.
old-location: storage\hwscsiwmiquerydatablock.htm
old-project: storage
ms.assetid: a2e588b8-50d6-4bed-b50c-c42be24955f1
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
req.alt-api: HwScsiWmiQueryDataBlock
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

# PSCSIWMI_QUERY_DATABLOCK callback



## -description
A miniport driver's <b>HwScsiWmiQueryDataBlock</b> routine is called to obtain either a single instance or all instances of a data block. This routine is required.



## -prototype

````
BOOLEAN HwScsiWmiQueryDataBlock(
  _In_    PVOID                    Context,
  _In_    PSCSIWMI_REQUEST_CONTEXT DispatchContext,
  _In_    ULONG                    GuidIndex,
  _In_    ULONG                    InstanceIndex,
  _In_    ULONG                    InstanceCount,
  _Inout_ PULONG                   InstanceLengthArray,
  _In_    ULONG                    BufferAvail,
  _Out_   PUCHAR                   Buffer
);
````


## -parameters

### -param Context [in]

Points to the miniport driver-defined context value passed to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. 


### -param DispatchContext [in]

Points to the SCSIWMI_REQUEST_CONTEXT structure that the miniport driver passed to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. 


### -param GuidIndex [in]

Specifies the data block by its index into the list of GUIDs in the SCSI_WMILIB_CONTEXT structure that the miniport driver passed to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. 


### -param InstanceIndex [in]

If <b>HwScsiWmiQueryDataBlock</b> is called in response to an IRP_MN_QUERY_SINGLE_INSTANCE request, <i>InstanceIndex</i> specifies the instance to be queried. If <b>HwScsiWmiQueryDataBlock</b> is called in response to an IRP_MN_QUERY_ALL_DATA REQUEST, <i>InstanceIndex</i> is zero.


### -param InstanceCount [in]

If <b>HwScsiWmiQueryDataBlock</b> is called in response to an IRP_MN_QUERY_SINGLE_INSTANCE request, <i>InstanceCount</i> is 1. If <b>HwScsiWmiQueryDataBlock</b> is called in response to an IRP_MN_QUERY_ALL_DATA REQUEST, <i>InstanceCount</i> is the number of instances to be returned.


### -param InstanceLengthArray [in, out]

Points to an array of ULONGs that indicate the length of each instance of the data block to be returned. This array has <i>InstanceCount</i> elements. This value may be <b>NULL</b> when there is not enough space in the output buffer to fulfill the request. 


### -param BufferAvail [in]

Specifies the maximum number of bytes available to receive data in the buffer at <i>Buffer</i>.


### -param Buffer [out]

Points to the buffer to receive instance data. If the buffer is large enough to receive all of the data, the miniport driver writes instance data to the buffer with each instance aligned on an 8-byte boundary. If the buffer is too small to receive all of the data, the miniport driver calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a> with a status of SRB_STATUS_DATA_OVERRUN and sets <i>BufferUsed</i>  to the size of the output buffer needed to fulfill the request.


## -returns
<b>HwScsiWmiQueryDataBlock</b> returns SRB_STATUS_PENDING if the request is pending or a nonzero SRB status value if the request was completed.  The SRB status value returned by this routine is the same as what was passed in to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a>. Although the return value data type is BOOLEAN, the <b>HwScsiWmiQueryDataBlock</b> routine actually returns an SRB status value.


## -remarks
When a miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a> with a pointer to an initialized SCSI_WMILIB_CONTEXT structure and <i>MinorFunction</i> set to <b>Srb-&gt;WmiSubFunction</b>. The SCSI port driver calls the miniport driver's <b>HwScsiWmiQueryDataBlock</b> routine if <i>MinorFunction</i> indicates a request to obtain a single instance or all instances of a data block.

The miniport driver writes instance data to the buffer. For requests that do not pend, the miniport driver calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a> with an appropriate <i>SrbStatus</i> value before returning from <b>HwScsiWmiQueryDataBlock</b>. If the request pends, the miniport driver calls <b>ScsiPortWmiPostProcess</b> when the request is complete.


## -see-also
<dl>
<dt>
<a href="..\scsiwmi\ns-scsiwmi-_scsiwmilib_context.md">SCSI_WMILIB_CONTEXT</a>
</dt>
<dt>
<a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a>
</dt>
<dt>
<a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HwScsiWmiQueryDataBlock callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

