---
UID: NS:winbio_types._WINBIO_BIR_HEADER
title: "_WINBIO_BIR_HEADER"
author: windows-driver-content
description: The WINBIO_BIR_HEADER structure contains the Common Biometric Exchange File Format (CBEFF) Patron Format A information that describes the rest of the BIR.
old-location: biometric\winbio_bir_header.htm
old-project: biometric
ms.assetid: 5053b027-61a9-463a-967c-9e9ff1673b1c
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWINBIO_BIR_HEADER, PWINBIO_BIR_HEADER, PWINBIO_BIR_HEADER structure pointer [Biometric Devices], WINBIO_BIR_HEADER, WINBIO_BIR_HEADER structure [Biometric Devices], _WINBIO_BIR_HEADER, biometric.winbio_bir_header, biometric_ref_1e5e4af7-36a5-414b-8c26-7a266c38272c.xml, winbio_types/PWINBIO_BIR_HEADER, winbio_types/WINBIO_BIR_HEADER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winbio_types.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winbio_types.h
api_name:
-	WINBIO_BIR_HEADER
product: Windows
targetos: Windows
req.typenames: WINBIO_BIR_HEADER
req.product: Windows 10 or later.
---

# _WINBIO_BIR_HEADER structure
The WINBIO_BIR_HEADER structure contains the Common Biometric Exchange File Format (CBEFF) Patron Format A information that describes the rest of the BIR.

## Syntax
```
typedef struct _WINBIO_BIR_HEADER {
  USHORT                   ValidFields;
  WINBIO_BIR_VERSION       HeaderVersion;
  WINBIO_BIR_VERSION       PatronHeaderVersion;
  WINBIO_BIR_DATA_FLAGS    DataFlags;
  WINBIO_BIOMETRIC_TYPE    Type;
  WINBIO_BIOMETRIC_SUBTYPE Subtype;
  WINBIO_BIR_PURPOSE       Purpose;
  WINBIO_BIR_QUALITY       DataQuality;
  LARGE_INTEGER            CreationDate;
  struct {
    LARGE_INTEGER BeginDate;
    LARGE_INTEGER EndDate;
  } ValidityPeriod;
  WINBIO_REGISTERED_FORMAT BiometricDataFormat;
  WINBIO_REGISTERED_FORMAT ProductId;
} WINBIO_BIR_HEADER;
```

## Members


`ValidFields`

A Patron Format A bitmask that indicates which CBEFF optional fields are present in the BIR. For more information about all members of WINBIO_BIR_HEADER, follow the link in the Remarks section to the <i>NISTIR 6529-A Specification</i>.

`HeaderVersion`

A structure of type WINBIO_BIR_VERSION that specifies the CBEFF header version.

Versions are represented as 8-bit values of the form: 0x<i>NM</i>, where <i>N</i> is the major version and <i>M</i> is the minor version.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef UCHAR WINBIO_BIR_VERSION, *PWINBIO_BIR_VERSION;</pre>
</td>
</tr>
</table></span></div>

`PatronHeaderVersion`

A structure of type WINBIO_BIR_VERSION that specifies PATRON_HEADER_VERSION.

`DataFlags`

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536461">WINBIO_BIR_DATA_FLAGS</a> that specifies the level of processing expected for a data capture.

`Type`

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536458">WINBIO_BIOMETRIC_TYPE</a> that specifies the biometric type.

`Subtype`

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536457">WINBIO_BIOMETRIC_SENSOR_SUBTYPE</a> that specifies the biometric subtype.

`Purpose`

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536463">WINBIO_BIR_PURPOSE</a> that specifies the intended use of the data.

`DataQuality`

A structure of type WINBIO_BIR_QUALITY that specifies the biometric data quality. Quality measurements are represented as signed integers in the range 0-100, except:

-1  Quality measurements are supported by the BIR creator, but no value is set in the BIR.

-2  Quality measurements are not supported by the BIR creator.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef CHAR WINBIO_BIR_QUALITY, *PWINBIO_BIR_QUALITY;</pre>
</td>
</tr>
</table></span></div>

`CreationDate`

Specifies the creation date and time of this BIR in UTC by using the format YYYYMMDDhhmmss.

`ValidityPeriod`

Specifies the validity period of this BIR by using the format described in <i>CreationDate</i>.

`BiometricDataFormat`

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536473">WINBIO_REGISTERED_FORMAT</a> that specifies the data format of the <b>StandardDataBlock</b> for this <a href="https://msdn.microsoft.com/library/windows/hardware/ff536459">WINBIO_BIR</a>.

`ProductId`

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536473">WINBIO_REGISTERED_FORMAT</a> that specifies the product identifier for the component that generated the <b>StandardDataBlock</b> for this WINBIO_BIR.

## Remarks
You can find more information about the fields of the standard biometric header in the <a href="http://go.microsoft.com/fwlink/p/?linkid=133328">NISTIR 6529-A Specification</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | winbio_types.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536459">WINBIO_BIR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536460">WINBIO_BIR_DATA</a>