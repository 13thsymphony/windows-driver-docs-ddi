---
UID : NF:mcd.ChangerInitializeElementStatus
title : ChangerInitializeElementStatus function
author : windows-driver-content
description : ChangerInitializeElementStatus handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS.
old-location : storage\changerinitializeelementstatus.htm
old-project : storage
ms.assetid : 1f8f13e0-b0d3-4c94-bd1f-0e42bb75142d
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.changerinitializeelementstatus, chgrmini_2aa82220-731a-49b0-b3e5-1db93f8e6dc0.xml, mcd/ChangerInitializeElementStatus, ChangerInitializeElementStatus function [Storage Devices], ChangerInitializeElementStatus
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : mcd.h
req.include-header : Mcd.h, Ntddchgr.h
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : LAMP_INTENSITY_WHITE
---


# ChangerInitializeElementStatus function
<b>ChangerInitializeElementStatus</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_initialize_element_status.md">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a>.

## Syntax

````
NTSTATUS ChangerInitializeElementStatus(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````

## Parameters

`DeviceObject`

Pointer to the device object that represents the changer.

`Irp`

Pointer to the IRP.


## Return Value

<b>ChangerInitializeElementStatus</b> returns the status returned by the system port driver or one of the following values:
      

STATUS_SUCCESS

STATUS_INVALID_PARAMETER

STATUS_INSUFFICIENT_RESOURCES

If the changer does not support initializing a range of elements of a particular type and ChangerInitializeElementStatus is called with an element type other than AllElements, it returns STATUS_INVALID_PARAMETER.

## Remarks

This routine is required.

<b>ChangerInitializeElementStatus</b> updates the changer's internal memory with current information about its elements.

The changer class driver checks the input buffer length in the I/O stack location before calling <b>ChangerInitializeElementStatus</b>.

<i>Irp</i><b>-&gt;SystemBuffer</b> points to a <a href="..\ntddchgr\ns-ntddchgr-_changer_initialize_element_status.md">CHANGER_INITIALIZE_ELEMENT_STATUS</a> structure as an input parameter that indicates the elements for which to initialize status and whether to initialize element status with data obtained from bar code labels. 

For a SCSI changer, <b>ChangerInitializeElementStatus</b> builds an SRB with a CDB to initialize element status, translates zero-based element addresses to device-specific addresses, and sends the SRB to the system port driver. 

<b>ChangerInitializeElementStatus</b> sets the <b>Information</b> field in the I/O status block to <b>sizeof</b>(CHANGER_INITIALIZE_ELEMENT_STATUS) before returning to the changer class driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | mcd.h (include Mcd.h, Ntddchgr.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntddchgr\ns-ntddchgr-_changer_initialize_element_status.md">CHANGER_INITIALIZE_ELEMENT_STATUS</a>

<a href="..\mcd\nf-mcd-changergetelementstatus.md">ChangerGetElementStatus</a>

<a href="..\ntddchgr\ns-ntddchgr-_changer_element_list.md">CHANGER_ELEMENT_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ChangerInitializeElementStatus function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>