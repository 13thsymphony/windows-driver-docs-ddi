---
UID : NI:bthioctl.IOCTL_BTH_SDP_SERVICE_SEARCH
title : IOCTL_BTH_SDP_SERVICE_SEARCH
author : windows-driver-content
description : The IOCTL_BTH_SDP_SERVICE_SEARCH request contacts a remote device with an SDP request for handles to SDP records of a particular service class or classes.
old-location : bltooth\ioctl_bth_sdp_service_search.htm
old-project : bltooth
ms.assetid : aea2aff2-5983-4583-9cc8-a45401ecdfb6
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : _HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : bthioctl.h
req.include-header : Bthioctl.h
req.target-type : Windows
req.target-min-winverclnt : Versions: Supported in Windows Vista, and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_BTH_SDP_SERVICE_SEARCH
req.alt-loc : Bthioctl.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= PASSIVE_LEVEL
req.typenames : "*PHFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1"
---

# IOCTL_BTH_SDP_SERVICE_SEARCH IOCTL
The IOCTL_BTH_SDP_SERVICE_SEARCH request contacts a remote device with an SDP request for handles to
     SDP records of a particular service class or classes.



The IOCTL_BTH_SDP_SERVICE_SEARCH request contacts a remote device with an SDP request for handles to
     SDP records of a particular service class or classes.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member contains a 
      <a href="..\bthioctl\ns-bthioctl-_bth_sdp_service_search_request.md">
      BTH_SDP_SERVICE_SEARCH_REQUEST</a> structure that specifies the connection handle to the remote SDP
      server and an array of GUIDs to search for.

### Input Buffer Length
The length of a 
      <a href="..\bthioctl\ns-bthioctl-_bth_sdp_service_search_request.md">
      BTH_SDP_SERVICE_SEARCH_REQUEST</a> structure/

### Output Buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that contains a variable length array of
      unsigned long integer values. Each value represents a remote SDP service record.

### Output Buffer Length
Callers can determine
      the length of this array by dividing the 
      <b>Information</b> member of the STATUS_BLOCK structure by 
      <code>sizeof(ULONG)</code>.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the output
      buffer. Otherwise, the 
      <b>Information</b> member is set to zero.

The 
      <b>Status</b> member is set to one of values in the following table.

STATUS_SUCCESS

The IOCTL completed successfully.

STATUS_DEVICE_NOT_CONNECTED

The device on which the SDP service resides was not connected.

STATUS_INSUFFICIENT_RESOURCES

There was not enough memory to complete this operation.

STATUS_INVALID_BUFFER_SIZE

The output buffer was sized incorrectly.

STATUS_INVALID_PARAMETER

One of the values in the input buffer was not valid.

STATUS_REQUEST_NOT_ACCEPTED

The SDP service rejected the request.

STATUS_TOO_MANY_GUIDS_REQUESTED

The SDP service could not process the number of GUIDs passed in the input buffer.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | bthioctl.h (include Bthioctl.h) |
| **IRQL** | <= PASSIVE_LEVEL |

    ## See Also

        <dl>
<dt>
<a href="..\bthioctl\ns-bthioctl-_bth_sdp_service_search_request.md">BTH_SDP_SERVICE_SEARCH_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_BTH_SDP_SERVICE_SEARCH control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>