---
UID: NS.NTDDCHGR._CHANGER_PRODUCT_DATA
title: _CHANGER_PRODUCT_DATA
author: windows-driver-content
description: The CHANGER_PRODUCT_DATA structure is used in conjunction with the IOCTL_CHANGER_GET_PRODUCT_DATA request to retrieve product data for a device.
old-location: storage\changer_product_data.htm
old-project: storage
ms.assetid: 18e5b394-b0ea-481c-b634-83a2ebec4784
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _CHANGER_PRODUCT_DATA, CHANGER_PRODUCT_DATA, *PCHANGER_PRODUCT_DATA
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
req.alt-api: CHANGER_PRODUCT_DATA
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
---

# _CHANGER_PRODUCT_DATA structure



## -description
The CHANGER_PRODUCT_DATA structure is used in conjunction with the <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_product_data.md">IOCTL_CHANGER_GET_PRODUCT_DATA</a> request to retrieve product data for a device. 



## -syntax

````
typedef struct _CHANGER_PRODUCT_DATA {
  UCHAR VendorId[VENDOR_ID_LENGTH];
  UCHAR ProductId[PRODUCT_ID_LENGTH];
  UCHAR Revision[REVISION_LENGTH];
  UCHAR SerialNumber[SERIAL_NUMBER_LENGTH];
  UCHAR DeviceType;
} CHANGER_PRODUCT_DATA, *PCHANGER_PRODUCT_DATA;
````


## -struct-fields

### -field VendorId

Specifies the name of the device manufacturer. 


### -field ProductId

Specifies the product identification as defined by the vendor.


### -field Revision

Specifies the product revision as defined by the vendor.


### -field SerialNumber

Specifies the value defined by the vendor to identify this device. Serial numbers are unique for all changers of a given type, but are not necessarily unique across vendor and product lines. For a SCSI changer, this value might be from Vital Product Data. If <b>SerialNumber</b> is not unique, the miniclass driver should not set the CHANGER_SERIAL_NUMBER_VALID flag in the <b>Features0</b> member of the <a href="storage.get_changer_parameters">GET_CHANGER_PARAMETERS</a> structure. 


### -field DeviceType

Specifies the device type of the changer. This member must be MEDIUM_CHANGER.


## -remarks


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
<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_product_data.md">IOCTL_CHANGER_GET_PRODUCT_DATA</a>
</dt>
<dt>
<a href="storage.changergetproductdata">ChangerGetProductData</a>
</dt>
<dt>
<a href="storage.get_changer_parameters">GET_CHANGER_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_PRODUCT_DATA structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

