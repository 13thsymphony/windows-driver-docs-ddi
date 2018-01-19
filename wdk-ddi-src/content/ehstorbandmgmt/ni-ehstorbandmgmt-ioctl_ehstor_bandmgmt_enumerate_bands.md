---
UID : NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS
title : IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS
author : windows-driver-content
description : This IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS request is sent to retrieve the list of bands for a storage device under band management. Banding information is returned in a table of band entries that includes band location and security properties.
old-location : storage\ioctl_ehstor_bandmgmt_enumerate_bands.htm
old-project : storage
ms.assetid : 80F7546C-3683-460B-A0D9-AD41386E6195
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _DXVA_VideoSample32, DXVA_VideoSample32
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ehstorbandmgmt.h
req.include-header : EhStorBandMgmt.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with  Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS
req.alt-loc : EhStorBandMgmt.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : DXVA_VideoSample32
---

# IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS IOCTL
This <b>IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</b> request is sent to retrieve the list of bands for a storage device under band management. Banding information is returned in a table of band entries that includes band location and security properties.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> must contain an <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_enumerate_bands_parameters.md">ENUMERATE_BANDS_PARAMETERS</a> structure.

### Input Buffer Length
<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (ENUMERATE_BANDS_PARAMETERS).

### Output Buffer
The buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> contains a <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_enumerate_bands_parameters.md">BAND_TABLE</a> structure followed by <b>BandTableEntryCount</b> band entries.

### Output Buffer Length
The length of a <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_enumerate_bands_parameters.md">BAND_TABLE</a> structure followed by <b>BandTableEntryCount</b> band entries.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
The <b>Information</b> field contains the number of bytes returned in the output buffer. One of the following values can be returned in the <b>Status</b> field.

    ## Remarks
        A driver or application can query for the necessary output buffer size by setting the output buffer for the request to NULL and the output size to 0. The <b>IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</b> request will return with the <b>Status</b> field of the <i>IoStatus</i> block set to STATUS_BUFFER_OVERFLOW and the <b>Information</b> field will contain the required buffer size.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ehstorbandmgmt.h (include EhStorBandMgmt.h) |
| **IRQL** |  |

    ## See Also

        <dl>
<dt>
<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_enumerate_bands_parameters.md">BAND_TABLE</a>
</dt>
<dt><b>ENUMERATE_BANDS_PARAMETERS</b></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>