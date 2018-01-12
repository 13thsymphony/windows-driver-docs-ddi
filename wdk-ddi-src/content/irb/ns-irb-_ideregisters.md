---
UID: NS:irb._IDEREGISTERS
title: _IDEREGISTERS
author: windows-driver-content
description: The IDEREGISTERS structure is used to report the contents of the IDE controller registers.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ideregisters.htm
old-project: storage
ms.assetid: a3df8ce0-4414-49d1-a02c-3f5a3efc0de2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _IDEREGISTERS, *PIDEREGISTERS, IDEREGISTERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: irb.h
req.include-header: Irb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDEREGISTERS
req.alt-loc: irb.h
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
req.typenames: *PIDEREGISTERS, IDEREGISTERS
---

# _IDEREGISTERS structure



## -description
The IDEREGISTERS structure is used to report the contents of the IDE controller registers.



## -syntax

````
typedef struct _IDEREGISTERS {
  UCHAR bFeaturesReg;
  UCHAR bSectorCountReg;
  UCHAR bSectorNumberReg;
  UCHAR bCylLowReg;
  UCHAR bCylHighReg;
  UCHAR bDriveHeadReg;
  UCHAR bCommandReg;
  UCHAR bReserved;
} IDEREGISTERS, *PIDEREGISTERS;
````


## -struct-fields

### -field bFeaturesReg

Specifies the contents of the ATA features register.


### -field bSectorCountReg

Specifies the contents of the ATA Sector Count register.


### -field bSectorNumberReg

Specifies the contents of the ATA Sector Number register.


### -field bCylLowReg

Specifies the contents of the ATA Cylinder Low register.


### -field bCylHighReg

Specifies the contents of the ATA Cylinder High register.


### -field bDriveHeadReg

Specifies the contents of the ATA Device/Head register.


### -field bCommandReg

Specifies the contents of the ATA Command register.


### -field bReserved

Reserved for future use. The miniport driver shall not use this field.


## -remarks
The information reported in the IDEREGISTERS structure is intended to be a superset of the information contained in <a href="..\ntdddisk\ns-ntdddisk-_ideregs.md">IDEREGS</a>. Microsoft might expand the contents of the IDEREGISTERS structure in the future. If you need a structure whose size is stable across different versions of the operating system, you should use <b>IDEREGS</b>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Irb.h (include Irb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntdddisk\ns-ntdddisk-_ideregs.md">IDEREGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IDEREGISTERS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

