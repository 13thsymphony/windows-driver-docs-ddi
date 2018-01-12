---
UID: NS:ntddchgr._CHANGER_ELEMENT_STATUS_EX
title: _CHANGER_ELEMENT_STATUS_EX
author: windows-driver-content
description: The ChangerGetElementStatus routine returns status information in this structure.
old-location: storage\changer_element_status_ex.htm
old-project: storage
ms.assetid: 1fb0d0f9-711a-4bd4-baf6-38ccbeae6e4a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _CHANGER_ELEMENT_STATUS_EX, CHANGER_ELEMENT_STATUS_EX, *PCHANGER_ELEMENT_STATUS_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddchgr.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CHANGER_ELEMENT_STATUS_EX
req.alt-loc: ntddchgr.h
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
req.typenames: CHANGER_ELEMENT_STATUS_EX, *PCHANGER_ELEMENT_STATUS_EX
---

# _CHANGER_ELEMENT_STATUS_EX structure



## -description
The <a href="..\mcd\nf-mcd-changergetelementstatus.md">ChangerGetElementStatus</a> routine returns status information in this structure. 



## -syntax

````
typedef struct _CHANGER_ELEMENT_STATUS_EX {
  CHANGER_ELEMENT Element;
  CHANGER_ELEMENT SrcElementAddress;
  ULONG           Flags;
  ULONG           ExceptionCode;
  UCHAR           TargetId;
  UCHAR           Lun;
  USHORT          Reserved;
  UCHAR           PrimaryVolumeID[MAX_VOLUME_ID_SIZE];
  UCHAR           AlternateVolumeID[MAX_VOLUME_ID_SIZE];
  UCHAR           VendorIdentification[VENDOR_ID_LENGTH];
  UCHAR           ProductIdentification[PRODUCT_ID_LENGTH];
  UCHAR           SerialNumber[SERIAL_NUMBER_LENGTH];
} CHANGER_ELEMENT_STATUS_EX, *PCHANGER_ELEMENT_STATUS_EX;
````


## -struct-fields

### -field Element

Specifies the element of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>  to which this structure refers.


### -field SrcElementAddress

Specifies the element of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a> from which the media currently in this element was most recently moved. This member is valid only if ELEMENT_STATUS_SVALID is also set in <b>Flags</b>. This value must be a zero-based offset from the device-unique value.


### -field Flags

Indicates the status of the element, which can be one or more of the following values.


### -field ELEMENT_STATUS_FULL

<dd>
The element contains a piece of media. This flag is valid if <b>ElementType</b> in the <b>Element</b> member is <b>ChangerDrive</b>, <b>ChangerSlot</b>, or <b>ChangerTransport</b>. If <b>ElementType</b> is <b>ChangerIEPort</b>, this flag is valid only if CHANGER_REPORT_IEPORT_STATE is also set in <b>Features0</b> of <a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>.


### -field ELEMENT_STATUS_IMPEXP

<dd>
The media in this element was placed there by an operator. This flag is valid only if <b>ElementType</b> in the <b>Element</b> member is <b>ChangerIEPort</b>. 


### -field ELEMENT_STATUS_EXCEPT

<dd>
The element is in an abnormal state. Check the <b>ExceptionCode</b> member for more information.


### -field ELEMENT_STATUS_ACCESS

<dd>
The changer's transport element can access the piece of media in this element. The miniclass driver clears this flag to indicate that the media is not accessible for one of the following reasons: If <b>ElementType</b> in the <b>Element</b> member is <b>ChangerSlot</b>, the slot is not present in the changer (for example, the magazine containing the slot has been physically removed). If <b>ElementType</b> is <b>ChangerDrive</b>, the drive is broken or has been removed. If <b>ElementType</b> is <b>ChangerIEPort</b>, the IEport is extended.


### -field ELEMENT_STATUS_EXENAB

<dd>
The element supports export of media through the changer's IEport.


### -field ELEMENT_STATUS_INENAB

<dd>
The element supports import of media through the changer's IEport.


### -field ELEMENT_STATUS_LUN_VALID

<dd>
The device number in the <b>Lun</b> member is valid. This flag is valid only if <b>ElementType</b> in the <b>Element</b> member is <b>ChangerDrive</b>. 


### -field ELEMENT_STATUS_ID_VALID

<dd>
The SCSI target ID in the <b>TargetID</b> member is valid. This flag is valid only if <b>ElementType</b> in the <b>Element</b> member is <b>ChangerDrive</b>. 


### -field ELEMENT_STATUS_NOT_BUS

<dd>
The drive at the address indicated by <b>Lun</b> and <b>TargetID</b> is on a different SCSI bus than the changer itself. 


### -field ELEMENT_STATUS_PRODUCT_DATA

<dd>
The serial number in the <b>SerialNumber</b> member is valid.


### -field ELEMENT_STATUS_INVERT

<dd>
The media in the element was flipped. This flag is valid only if the ELEMENT_STATUS_SVALID flag is also set.


### -field ELEMENT_STATUS_SVALID

<dd>
The <b>SourceElement</b> member and ELEMENT_STATUS_INVERT flag are both valid.


### -field ELEMENT_STATUS_PVOLTAG

<dd>
Primary volume information in the <b>PrimaryVolumeID</b> member is valid.


### -field ELEMENT_STATUS_AVOLTAG

<dd>
Alternate volume information in the <b>AlternateVolumeID</b> member is valid.

</dd>
</dl>

### -field ExceptionCode

Indicates that the element is in an abnormal state. This member is valid only if ELEMENT_STATUS_EXCEPT is set in <b>Flags</b>. <b>ExceptionCode</b> can be set to one of the following values. 


### -field ERROR_LABEL_UNREADABLE

<dd>
The changer's bar code reader could not read the bar code label on the piece of media in this element, because the media is missing, damaged, improperly positioned, or upside down.


### -field ERROR_LABEL_QUESTIONABLE

<dd>
The label might be invalid due to a unit attention condition.


### -field ERROR_SLOT_NOT_PRESENT

<dd>
The slot at this element address is currently not installed in the changer. A miniclass driver sets this code for each slot in a removable magazine to indicate that the magazine has been removed.


### -field ERROR_DRIVE_NOT_INSTALLED

<dd>
The drive at this element address is absent. If a changer can continue to operate without the drive, its miniclass driver sets ERROR_DRIVE_NOT_INSTALLED for the drive. 


### -field ERROR_TRAY_MALFUNCTION

<dd>
The drive at this element address has a tray that must be extended to load or remove media, and the tray is not extending as required.


### -field ERROR_UNHANDLED_ERROR

<dd>
Unknown error condition.

</dd>
</dl>

### -field TargetId

Specifies the SCSI target ID of the drive at this element address for a SCSI changer. This member is valid only if <b>ElementType</b> in the <b>Element</b> member is <b>ChangerDrive</b> and ELEMENT_STATUS_ID_VALID is set in <b>Flags</b>. 


### -field Lun

Specifies the SCSI device number of the drive at this element address. This member is valid only if <b>ElementType</b> in the <b>Element</b> member is <b>ChangerDrive</b> and ELEMENT_STATUS_LUN_VALID is set in <b>Flags</b>.


### -field Reserved

Reserved for future use. The value of this member must be zero.


### -field PrimaryVolumeID

Specifies the primary volume identifier for the media. If the changer supports a bar code reader and the reader is installed (as indicated by CHANGER_BAR_CODE_SCANNER_INSTALLED in <b>Features0</b> of <a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>), the miniclass driver must set <b>PrimaryVolumeID</b> to the bar code of the media. If the changer does not support a bar code reader, the miniclass driver should set <b>PrimaryVolumeID</b> to the value previously assigned to the media using the <a href="..\mcd\nf-mcd-changerqueryvolumetags.md">ChangerQueryVolumeTags</a> routine with an ASSERT_PRIMARY or REPLACE_PRIMARY action. This member is valid only if ELEMENT_STATUS_PVOLTAG is also set in <b>Flags</b>. If the volume identifier is missing or unreadable, the miniclass driver should clear this flag and set the appropriate error status. This identifier must be no larger than MAX_VOLUME_ID_SIZE bytes. 


### -field AlternateVolumeID

Specifies alternate volume identification for the media. This member is valid for two-sided media only, and pertains to the ID of the inverted side. It never represents a bar code. The miniclass driver must set <b>AlternateVolumeID</b> to the value previously assigned to the media using the <a href="..\mcd\nf-mcd-changerqueryvolumetags.md">ChangerQueryVolumeTags</a> routine with an ASSERT_ALTERNATE or REPLACE_ALTERNATE action. The identifier must be no larger than MAX_VOLUME_ID_SIZE bytes and is valid only if ELEMENT_STATUS_AVOLTAG is also set in <b>Flags</b>.


### -field VendorIdentification

Contains the vendor ID. This identifier must be no larger than VENDOR_ID_LENGTH bytes. 


### -field ProductIdentification

Contains the product ID. This identifier must be no larger than PRODUCT_ID_LENGTH bytes. 


### -field SerialNumber

Contains the serial number. This identifier must be no larger than SERIAL_NUMBER_LENGTH bytes. 


## -remarks
The <a href="..\mcd\nf-mcd-changergetelementstatus.md">ChangerGetElementStatus</a> routine returns status information in this structure if vendor, product, or serial number information is needed. Otherwise, <b>ChangerGetElementStatus</b> returns status information in the <a href="..\ntddchgr\ns-ntddchgr-_changer_element_status.md">CHANGER_ELEMENT_STATUS</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddchgr.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddchgr\ns-ntddchgr-_changer_element_status.md">CHANGER_ELEMENT_STATUS</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changergetelementstatus.md">ChangerGetElementStatus</a>
</dt>
<dt>
<a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>
</dt>
<dt>
<a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_element_status.md">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_ELEMENT_STATUS_EX structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

