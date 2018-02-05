---
UID : NS:ntddcdvd._DVD_LAYER_DESCRIPTOR
title : "_DVD_LAYER_DESCRIPTOR"
author : windows-driver-content
description : The DVD_LAYER_DESCRIPTOR structure is used in conjunction with the IOCTL_DVD_READ_STRUCTURE request to retrieve a DVD layer descriptor.
old-location : storage\dvd_layer_descriptor.htm
old-project : storage
ms.assetid : dd981cc1-ab82-49de-8cf1-ba2b7451c7ef
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : PDVD_LAYER_DESCRIPTOR structure pointer [Storage Devices], DVD_LAYER_DESCRIPTOR structure [Storage Devices], ntddcdvd/PDVD_LAYER_DESCRIPTOR, storage.dvd_layer_descriptor, structs-DVD_94f08da1-fe98-47cd-989a-b3f574874d6b.xml, DVD_LAYER_DESCRIPTOR, ntddcdvd/DVD_LAYER_DESCRIPTOR, PDVD_LAYER_DESCRIPTOR, *PDVD_LAYER_DESCRIPTOR, _DVD_LAYER_DESCRIPTOR
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddcdvd.h
req.include-header : Ntddcdvd.h
req.target-type : Windows
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
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDVD_LAYER_DESCRIPTOR, DVD_LAYER_DESCRIPTOR"
---

# _DVD_LAYER_DESCRIPTOR structure
The DVD_LAYER_DESCRIPTOR structure is used in conjunction with the <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_structure.md">IOCTL_DVD_READ_STRUCTURE</a> request to retrieve a DVD layer descriptor.

## Syntax
````
typedef struct _DVD_LAYER_DESCRIPTOR {
  UCHAR BookVersion  :4;
  UCHAR BookType  :4;
  UCHAR MinimumRate  :4;
  UCHAR DiskSize  :4;
  UCHAR LayerType  :4;
  UCHAR TrackPath  :1;
  UCHAR NumberOfLayers  :2;
  UCHAR Reserved1  :1;
  UCHAR TrackDensity  :4;
  UCHAR LinearDensity  :4;
  ULONG StartingDataSector;
  ULONG EndDataSector;
  ULONG EndLayerZeroSector;
  UCHAR Reserved5  :7;
  UCHAR BCAFlag  :1;
} DVD_LAYER_DESCRIPTOR, *PDVD_LAYER_DESCRIPTOR;
````

## Members


`BCAFlag`

Indicates, if set to 1, the presence of data in the burst cutting area (BCA). If set to zero, it indicates that there is no BCA data.

`BookType`

Specifies the DVD book this media complies with. This member can have one of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
DVD-ROM

</td>
</tr>
<tr>
<td>
1

</td>
<td>
DVD-RAM

</td>
</tr>
<tr>
<td>
2

</td>
<td>
DVD-R

</td>
</tr>
<tr>
<td>
3

</td>
<td>
DVD-RW

</td>
</tr>
<tr>
<td>
9

</td>
<td>
DVD+RW

</td>
</tr>
</table>

`BookVersion`

Specifies the version of the specified book that this media complies with.

`DiskSize`

Specifies the physical size of the media. A value of zero indicates 120 mm. A value of 1 indicates a size of 80 mm.

`EndDataSector`

Specifies the last sector of the user data in the last layer of the media.

`EndLayerZeroSector`

Specifies the last sector of the user data in layer zero. If this media does not use the opposite track path method and contains multiple layers, this value is set to zero.

`LayerType`

Indicates the type of layer. This member can have one of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
1

</td>
<td>
Read-only layer

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Recordable layer

</td>
</tr>
<tr>
<td>
4

</td>
<td>
Rewritable layer

</td>
</tr>
</table>

`LinearDensity`

Indicates the minimum/maximum pit length used for this layer in units of micrometers per bit. This member can have one of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
0.267 m/bit

</td>
</tr>
<tr>
<td>
1

</td>
<td>
0.293 m/bit

</td>
</tr>
<tr>
<td>
2

</td>
<td>
0.409 to 0.435 m/bit

</td>
</tr>
<tr>
<td>
4

</td>
<td>
0.280 to 0.291 m/bit

</td>
</tr>
<tr>
<td>
8

</td>
<td>
0.353 m/bit

</td>
</tr>
</table>

`MinimumRate`

Specifies the read rate to use for the media. This member can have one of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
DVD-ROM

</td>
</tr>
<tr>
<td>
1

</td>
<td>
DVD-RAM

</td>
</tr>
<tr>
<td>
2

</td>
<td>
DVD-R

</td>
</tr>
<tr>
<td>
3

</td>
<td>
DVD-RW

</td>
</tr>
<tr>
<td>
9

</td>
<td>
DVD+RW

</td>
</tr>
</table>

`NumberOfLayers`

Specifies the number of layers present on the side of the media being read. A value of zero indicates that the media has one layer. A value of 1 indicates that the media has two layers.

`Reserved1`

Reserved.

`Reserved5`

Reserved.

`StartingDataSector`

Specifies the first block that contains user data. This member can have one of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0x30000

</td>
<td>
An initial block value of 0x30000 indicates that the media type is DVD-ROM or DVD-R/-RW

</td>
</tr>
<tr>
<td>
0x31000

</td>
<td>
An initial block value of 0x30000 indicates that the media type is DVD-RAM or DVD+RW

</td>
</tr>
</table>

`TrackDensity`

Indicates the track width used for this media in units of micrometers per track. This member can have one of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
0.74 m/track

</td>
</tr>
<tr>
<td>
1

</td>
<td>
0.80 m/track

</td>
</tr>
<tr>
<td>
2

</td>
<td>
0.615 m/track

</td>
</tr>
</table>

`TrackPath`

Specifies the direction of the layers when more than one layer is used. If the <b>TrackPath</b> member is zero, this media uses a parallel track path (PTP). With PTP, each layer is independent and has its own lead-in and lead-out areas. If <b>TrackPath</b> is 1, the media uses opposite track path (OTP). With opposite track path, the two layers are united, and there is only one lead-in and lead-out area. For further details, see the <i>SCSI Multimedia Commands - 3 (MMC-3) </i>specification.

## Remarks
For more information, see the <i>SCSI Multimedia Commands - 3 (MMC-3) </i>specification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdvd.h (include Ntddcdvd.h) |

## See Also

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_structure.md">IOCTL_DVD_READ_STRUCTURE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DVD_LAYER_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>