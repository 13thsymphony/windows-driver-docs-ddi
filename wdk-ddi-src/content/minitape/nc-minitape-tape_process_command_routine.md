---
UID: NC:minitape.TAPE_PROCESS_COMMAND_ROUTINE
title: TAPE_PROCESS_COMMAND_ROUTINE
author: windows-driver-content
description: TAPE_PROCESS_COMMAND_ROUTINE handles the device-specific aspects of an IOCTL request.
old-location: storage\tapeminicreatepartition.htm
old-project: storage
ms.assetid: 6675d840-8b13-44ef-bbdb-84d683240175
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _PROCESSOR_NUMBER, *PPROCESSOR_NUMBER, PROCESSOR_NUMBER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: minitape.h
req.include-header: Minitape.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: (*TAPE_PROCESS_COMMAND_ROUTINE)
req.alt-loc: minitape.h
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
req.typenames: *PPROCESSOR_NUMBER, PROCESSOR_NUMBER
---

# TAPE_PROCESS_COMMAND_ROUTINE callback



## -description
<i>TAPE_PROCESS_COMMAND_ROUTINE</i> handles the device-specific aspects of an IOCTL request.



## -prototype

````
TAPE_PROCESS_COMMAND_ROUTINE (*TAPE_PROCESS_COMMAND_ROUTINE);

TAPE_STATUS (*TAPE_PROCESS_COMMAND_ROUTINE)(
  _Inout_  PVOID               MinitapeExtension,
  _Inout_  PVOID               CommandExtension,
  _Inout_  PVOID               CommandParameters,
  _Inout_  PSCSI_REQUEST_BLOCK Srb,
  _In_     ULONG               CallNumber,
  _In_opt_ TAPE_STATUS         StatusOfLastCommand,
  _Inout_  PULONG              RetryFlags
)
{ ... }
````


## -parameters

### -param MinitapeExtension [in, out]

Pointer to the driver-specific minitape extension. This is <b>NULL</b> if the miniclass driver did not request a minitape extension when it initialized.


### -param CommandExtension [in, out]

Pointer to the command extension. This is <b>NULL</b> if the miniclass driver did not request a command extension when it initialized.


### -param CommandParameters [in, out]

Pointer to a buffer allocated by the caller that contains a <a href="..\ntddtape\ns-ntddtape-_tape_create_partition.md">TAPE_CREATE_PARTITION</a> structure.


### -param Srb [in, out]

Pointer to an SRB allocated and partially filled in by the tape class driver. <i>TAPE_PROCESS_COMMAND_ROUTINE</i> must fill in the CDB in the SRB. 

<ul>
<li>
<b>Cdb</b> - Pointer to the SCSI CDB for the command. Clear the CDB with <b>TapeClassZeroMemory</b> before filling it in.

</li>
<li>
<b>CdbLength</b> - Specifies the number of bytes in the CDB.

</li>
</ul>
<i>TAPE_PROCESS_COMMAND_ROUTINE</i> might also fill in the following members in the SRB:

<ul>
<li>
<b>DataBuffer</b> - Pointer to the data buffer to be transferred. Use <a href="..\minitape\nf-minitape-tapeclassallocatesrbbuffer.md">TapeClassAllocateSrbBuffer</a> to allocate a <b>DataBuffer</b> of length greater than or equal to <b>DataTransferLength</b>.

</li>
<li>
<b>DataTransferLength</b> - Specifies the number of bytes to be transferred in the SRB. This member is set by <b>TapeClassAllocateSrbBuffer</b>.

</li>
<li>
<b>TimeOutValue</b> - Specifies a time-out value for this command, overriding the default time-out value from the tape class driver's device extension.

</li>
<li>
<b>SrbFlags</b> - Specifies a flag for this command. The tape miniclass driver must set SRB_FLAGS_DATA_OUT if the SRB is sending data to the tape drive. This member can be zero if the SRB is requesting data from the tape drive or if no data is being transferred by the command.

</li>
</ul>

### -param CallNumber [in]

Specifies the number of times <i>TAPE_PROCESS_COMMAND_ROUTINE</i> has been called to process a given tape command. <i>CallNumber</i> is zero the first time this routine is called and is incremented for each subsequent call until the miniclass driver returns a <a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a> value that indicates the command is complete.


### -param StatusOfLastCommand [in, optional]

Specifies the status of the last command. In the first call to <i>TAPE_PROCESS_COMMAND_ROUTINE</i> to process a given request, <i>StatusOfLastCommand </i>is TAPE_STATUS_SUCCESS. In subsequent calls, <i>StatusOfLastCommand </i>is either TAPE_STATUS_SUCCESS or an error status if an error occurred and the tape miniclass driver set RETURN_ERRORS in <i>RetryFlags</i> in the previous call. 


### -param RetryFlags [in, out]

Pointer to a variable that specifies what action the tape class driver should take when a tape device reports an error.

The low-order word specifies the number of retries to perform in the event of a SCSI command failure. The default is zero (no retries).

The high-order word contains flags that specify how the tape class driver should return control if an error occurs:

<ul>
<li>
If RETURN_ERRORS and IGNORE_ERRORS are clear (the default) the tape class driver returns a failure status to the original requester.

</li>
<li>
If the miniclass driver sets RETURN_ERRORS, the tape class driver calls <i>TAPE_PROCESS_COMMAND_ROUTINE</i> with <i>StatusOfLastCommand</i> set to a failure status.

</li>
<li>
If the miniclass driver sets IGNORE_ERRORS, the tape class driver converts a failure status to success and calls <i>TAPE_PROCESS_COMMAND_ROUTINE</i> with <i>StatusOfLastCommand </i>set to success.

</li>
</ul>

## -returns
<dl>
<dt><b>TAPE_STATUS_SEND_SRB_AND_CALLBACK</b></dt>
</dl>Indicates to the tape class driver that the SRB has been filled in and is ready to be sent to the target device. By default, the tape class driver calls <i>TAPE_PROCESS_COMMAND_ROUTINE</i> again only if the SRB succeeds. A miniclass driver can modify the default behavior by setting <i>RetryFlags</i> before returning from <i>TAPE_PROCESS_COMMAND_ROUTINE</i>.
<dl>
<dt><b>TAPE_STATUS_CALLBACK</b></dt>
</dl>Directs the tape class driver to increment <i>CallNumber</i> and call <i>TAPE_PROCESS_COMMAND_ROUTINE</i> again without sending an SRB to the tape device. 
<dl>
<dt><b>TAPE_STATUS_CHECK_TEST_UNIT_READY</b></dt>
</dl>Directs the tape class driver to fill in an SRB for the TEST UNIT READY command and send the SRB to the device.
<dl>
<dt><b>TAPE_STATUS_<i>XXX</i></b></dt>
</dl>Any other return code indicates to the tape class driver that the command is complete and indicates success, failure, or warning. Possible completion return values for this routine include, but are not limited to:
<dl>
<dd>
TAPE_STATUS_SUCCESS

</dd>
<dd>
TAPE_STATUS_INSUFFICIENT_RESOURCES

</dd>
<dd>
TAPE_STATUS_INVALID_DEVICE_REQUEST

</dd>
<dd>
TAPE_STATUS_INVALID_PARAMETER

</dd>
<dd>
TAPE_STATUS_IO_DEVICE_ERROR

</dd>
<dd>
TAPE_STATUS_MEDIA_WRITE_PROTECTED

</dd>
<dd>
TAPE_STATUS_NOT_IMPLEMENTED

</dd>
</dl>TAPE_STATUS_SUCCESS

TAPE_STATUS_INSUFFICIENT_RESOURCES

TAPE_STATUS_INVALID_DEVICE_REQUEST

TAPE_STATUS_INVALID_PARAMETER

TAPE_STATUS_IO_DEVICE_ERROR

TAPE_STATUS_MEDIA_WRITE_PROTECTED

TAPE_STATUS_NOT_IMPLEMENTED

 


## -remarks
The following functions can be assigned to this callback placeholder:

<i>CreatePartition</i> handles the device-specific aspects of an <a href="..\ntddtape\ni-ntddtape-ioctl_tape_create_partition.md">IOCTL_TAPE_CREATE_PARTITION</a> request. This routine is required. <i>CreatePartition</i> creates a partition on a tape by filling in the CDB in an SRB passed by the tape class driver. Creating a partition typically requires a series of SRBs to complete the operation. After <i>CreatePartition</i> fills in a given SRB and returns, the tape class driver sends the SRB to the target device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>TapeMiniCreatePartition</i> again.

<i>CreatePartition</i> must fill in the following members in the SRB before returning to the tape class driver:

If the tape miniclass driver stores partition information in the minitape extension, <i>CreatePartition</i> updates the extension before returning to the tape class driver with TAPE_STATUS_SUCCESS.

<i>Erase</i> handles the device-specific aspects of an <a href="..\ntddtape\ni-ntddtape-ioctl_tape_erase.md">IOCTL_TAPE_ERASE</a> request. This routine is required. <i>Erase</i> erases a tape by filling in the CDB in an SRB passed by the tape class driver. Erasing a tape typically requires one SRB to complete the operation. After <i>Erase</i> fills in the SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>Erase</i> again. <i>Erase</i> then returns TAPE_STATUS_SUCCESS.

<i>GetDriveParameters</i> handles the device-specific aspects of an <a href="..\ntddtape\ni-ntddtape-ioctl_tape_get_drive_params.md">IOCTL_TAPE_GET_DRIVE_PARAMS</a> request. This routine is required. <i>GetDriveParameters</i> gets tape drive parameters by filling in the CDB in an SRB passed by the tape class driver. Getting drive parameters typically requires a series of SRBs to complete the operation. After <i>GetDriveParameters</i> fills in a given SRB and returns, the tape class driver sends the SRB to the target device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>GetDriveParameters</i> again. 

<i>GetMediaParameters</i> handles the device-specific aspects of an <a href="..\ntddtape\ni-ntddtape-ioctl_tape_get_media_params.md">IOCTL_TAPE_GET_MEDIA_PARAMS</a> request. This routine is required. <i>GetMediaParameters</i> gets tape media parameters by filling in the CDB in an SRB passed by the tape class driver. Getting media parameters typically requires more than one SRB to complete the operation, starting with a test unit ready which the miniclass driver requests by returning TAPE_STATUS_CHECK_TEST_UNIT_READY the first time the tape class driver calls the routine. 

After <i>GetMediaParameters</i> fills in a given SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls GetMediaParameters again. 

<i>GetMediaTypes</i> handles the device-specific aspects of an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_media_types_ex.md">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a> request. This routine is required. <i>GetMediaTypes</i> gets information about the media types supported by a tape device by filling in the CDB in an SRB passed by the tape class driver. Getting media types typically requires more than one SRB to complete the operation, starting with a test unit ready which the miniclass driver requests by returning TAPE_STATUS_CHECK_TEST_UNIT_READY the first time the tape class driver calls the routine. 

<i>GetPosition</i> handles the device-specific aspects of an <a href="..\ntddtape\ni-ntddtape-ioctl_tape_get_position.md">IOCTL_TAPE_GET_POSITION</a> request. This routine is required. <i>GetPosition</i> reads the position of a tape by filling in the CDB in an SRB passed by the tape class driver. Reading tape position typically requires more than one SRB to complete the operation, often starting with a test unit ready which the miniclass driver requests by returning TAPE_STATUS_CHECK_TEST_UNIT_READY the first time the tape class driver calls the routine. 

<i>GetStatus</i> handles the device-specific aspects of an <a href="..\ntddtape\ni-ntddtape-ioctl_tape_get_status.md">IOCTL_TAPE_GET_STATUS</a> request. This routine is required. <i>GetStatus</i> reads the status of a tape device, typically by directing the tape class driver to issue a test unit ready command. 

If a device indicates whether a drive needs cleaning in sense data (as opposed to reporting the need for cleaning as an error, which a miniclass driver would handle in its <a href="..\minitape\nc-minitape-tape_error_routine.md">TapeMiniTapeError</a> routine), <i>GetStatus</i> fills in the CDB in the SRB passed by the tape class driver to obtain the sense data and, if necessary, returns TAPE_STATUS_REQUIRES_CLEANING.

<i>Prepare</i> handles the device-specific aspects of an <a href="..\ntddtape\ni-ntddtape-ioctl_tape_prepare.md">IOCTL_TAPE_PREPARE</a> request. This routine is required. <i>Prepare</i> prepares a tape by filling in the CDB in an SRB passed by the tape class driver. If the device supports the requested operation, preparing a tape typically requires one SRB. After <i>Prepare</i> fills in the SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>Prepare</i> again.

<i>SetDriveParameters</i> handles the device-specific aspects of an <a href="..\ntddtape\ni-ntddtape-ioctl_tape_set_drive_params.md">IOCTL_TAPE_SET_DRIVE_PARAMS</a> request. This routine is required. <i>SetDriveParameters</i> sets parameters for a tape device by filling in the CDB in an SRB passed by the tape class driver. Setting parameters typically involves a series of SRBs to complete the operation. After <i>SetDriveParameters</i> fills in a given SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>SetDriveParameters</i> again.

<i>SetMediaParameters</i> handles the device-specific aspects of an <a href="..\ntddtape\ni-ntddtape-ioctl_tape_set_media_params.md">IOCTL_TAPE_SET_MEDIA_PARAMS</a> request. This routine is required. <i>SetMediaParameters</i> sets the block size of a tape by filling in the CDB in an SRB passed by the tape class driver. Setting the block size typically requires more than one SRB to complete the operation, starting with a test unit ready which the miniclass driver requests by returning TAPE_STATUS_CHECK_TEST_UNIT_READY the first time the tape class driver calls the routine. 

After <i>SetMediaParameters</i> fills in a given SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>SetMediaParameters</i> again. 

<i>SetPosition</i> handles the device-specific aspects of an <a href="..\ntddtape\ni-ntddtape-ioctl_tape_set_position.md">IOCTL_TAPE_SET_POSITION</a> request. This routine is required. <i>SetPosition</i> sets the position of a tape by filling in the CDB in an SRB passed by the tape class driver. Setting the position typically requires one SRB. After <i>SetPosition</i> fills in the SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>SetPosition</i> again. <i>SetPosition</i> then returns TAPE_STATUS_SUCCESS.

<i>WriteMarks</i> handles the device-specific aspects of an <a href="..\ntddtape\ni-ntddtape-ioctl_tape_write_marks.md">IOCTL_TAPE_WRITE_MARKS</a> request. This routine is required. <i>WriteMarks</i> writes marks to a tape by filling in the CDB in an SRB passed by the tape class driver. Writing marks typically takes one SRB to complete the operation. After <i>WriteMarks</i> fills in the SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>WriteMarks</i> again. <i>WriteMarks</i> then returns TAPE_STATUS_SUCCESS. 

<i>PreProcessReadWrite</i> is an optional, special-purpose routine that performs any device-specific operations required before read and write operations. Most tape miniclass drivers do not need this routine. The activities of the <i>PreProcessReadWrite</i> routine are device specific. The routine can use the information passed to it by the class driver to implement special preprocessing for reads and writes. If a drive has limited capabilities, the driver may need this routine to maintain coherent state, for example.

If a tape miniclass driver sets a non-<b>NULL</b> entry point for this routine in the TAPE_INIT_DATA_EX structure it passes to <a href="..\minitape\nf-minitape-tapeclassinitialize.md">TapeClassInitialize</a> from its <b>DriverEntry</b> routine, the tape class driver calls it before each read and write operation on the tape device. The class driver does not expect any information back from this routine.

<i>WMIOperations</i> is the common entry point for all WMI calls from the tape class driver. A minidriver that supports WMI should set the function pointer member, <b>WMIOperations</b>, in the structure TAPE_INIT_DATA_EX to point to the minidriver's <i>TAPE_PROCESS_COMMAND_ROUTINE</i> routine. The minidriver should do this in its DriverEntry routine before calling <a href="..\minitape\nf-minitape-tapeclassinitialize.md">TapeClassInitialize</a>. If a minidriver does not support WMI operations, it should set TapeWMIOperations field to <b>NULL</b>.

The tape class driver assigns values to the members of TAPE_WMI_OPERATIONS structure, and passes this structure to minidriver's <i>WMIOperations</i> routine in the <i>CommandParameters</i> parameter. As with other minidriver routines, <i>WMIOperations</i> fills, creates, and initializes the SCSI request blocks (SRB) and the command descriptor blocks (CDB) required to implement the indicated WMI method, and returns control to tape class driver. The tape class driver then calls the port driver to execute the request. 

The minidriver returns the WMI data in the buffer pointed to by the <b>DataBuffer</b> member of the TAPE_WMI_OPERATIONS structure.


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
<dt>Minitape.h (include Minitape.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="..\minitape\nf-minitape-tapeclassallocatesrbbuffer.md">TapeClassAllocateSrbBuffer</a>
</dt>
<dt>
<a href="..\minitape\nf-minitape-tapeclasszeromemory.md">TapeClassZeroMemory</a>
</dt>
<dt>
<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_PROCESS_COMMAND_ROUTINE routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

