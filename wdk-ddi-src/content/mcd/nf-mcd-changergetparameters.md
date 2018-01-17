---
UID: NF:mcd.ChangerGetParameters
title: ChangerGetParameters function
author: windows-driver-content
description: ChangerGetParameters handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_GET_PARAMETERS.
old-location: storage\changergetparameters.htm
old-project: storage
ms.assetid: c1f508a3-6aa8-4fed-af14-6466fcae30da
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ChangerGetParameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ChangerGetParameters
req.alt-loc: mcd.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: KSIDEFAULTCLOCK, *PKSIDEFAULTCLOCK
---

# ChangerGetParameters function



## -description
<b>ChangerGetParameters</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559399">IOCTL_CHANGER_GET_PARAMETERS</a>. 



## -syntax

````
NTSTATUS ChangerGetParameters(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````


## -parameters

### -param DeviceObject [in]

Pointer to the device object that represents the changer. 


### -param Irp [in]

Pointer to the IRP. 


## -returns
<b>ChangerGetParameters</b> returns the STATUS_<i>XXX</i> value returned by the system port driver or one of the following values:
      

STATUS_SUCCESS

STATUS_INFO_LENGTH_MISMATCH

STATUS_INSUFFICIENT_RESOURCES


## -remarks
This routine is required.

<b>ChangerGetParameters</b> returns the parameters of a changer, including the number and type of its elements and the functionality it supports.

The changer class driver checks the output buffer length in the I/O stack location before calling <b>ChangerGetParameters</b>. If the output buffer length is smaller than <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/ff554979">GET_CHANGER_PARAMETERS</a>) the changer class driver returns with a value of STATUS_INFO_LENGTH_MISMATCH. 

<b>ChangerGetParameters</b> retrieves parameter data from the device by building SRBs with CDBs to get the SCSI parameter header page, the element address page, the transport geometry page, and the device capabilities page, or the non-SCSI equivalent of this data. 

<b>ChangerGetParameters</b> then fills in a GET_CHANGER_PARAMETERS structure at <i>Irp</i><b>-&gt;AssociatedIrp.SystemBuffer</b> before returning to the changer class driver. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554979">GET_CHANGER_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559399">IOCTL_CHANGER_GET_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ChangerGetParameters function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

