---
UID: NS:ntddstor._DEVICE_MEDIA_INFO
title: "_DEVICE_MEDIA_INFO"
author: windows-driver-content
description: A storage class driver returns an array of DEVICE_MEDIA_INFO structures, embedded in a GET_MEDIA_TYPES structure, in response to an IOCTL_STORAGE_GET_MEDIA_TYPES_EX device-control request.
old-location: storage\device_media_info.htm
old-project: storage
ms.assetid: 87906511-7bcb-4f4d-9383-44b0501536e3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MEDIA_CURRENTLY_MOUNTED, *PDEVICE_MEDIA_INFO, DEVICE_MEDIA_INFO structure [Storage Devices], MEDIA_READ_WRITE, MEDIA_ERASEABLE, PDEVICE_MEDIA_INFO, structs-general_e2c363ff-f053-45be-a807-f90480c0ae1f.xml, ntddstor/PDEVICE_MEDIA_INFO, MEDIA_WRITE_PROTECTED, MEDIA_READ_ONLY, DEVICE_MEDIA_INFO, PDEVICE_MEDIA_INFO structure pointer [Storage Devices], _DEVICE_MEDIA_INFO, MEDIA_WRITE_ONCE, storage.device_media_info, ntddstor/DEVICE_MEDIA_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h, Minitape.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	DEVICE_MEDIA_INFO
product: Windows
targetos: Windows
req.typenames: "*PDEVICE_MEDIA_INFO, DEVICE_MEDIA_INFO"
---

# _DEVICE_MEDIA_INFO structure
A storage class driver returns an array of <b>DEVICE_MEDIA_INFO</b> structures, embedded in a <a href="..\ntddstor\ns-ntddstor-_get_media_types.md">GET_MEDIA_TYPES</a> structure, in response to an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_media_types_ex.md">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a> device-control request.

## Syntax
````
typedef struct _DEVICE_MEDIA_INFO {
  union {
    struct {
      LARGE_INTEGER      Cylinders;
      STORAGE_MEDIA_TYPE MediaType;
      ULONG              TracksPerCylinder;
      ULONG              SectorsPerTrack;
      ULONG              BytesPerSector;
      ULONG              NumberMediaSides;
      ULONG              MediaCharacteristics;
    } DiskInfo;
    struct {
      LARGE_INTEGER      Cylinders;
      STORAGE_MEDIA_TYPE MediaType;
      ULONG              TracksPerCylinder;
      ULONG              SectorsPerTrack;
      ULONG              BytesPerSector;
      ULONG              NumberMediaSides;
      ULONG              MediaCharacteristics;
    } RemovableDiskInfo;
    struct {
      STORAGE_MEDIA_TYPE MediaType;
      ULONG              MediaCharacteristics;
      ULONG              CurrentBlockSize;
      STORAGE_BUS_TYPE   BusType;
      union {
        struct {
          UCHAR MediumType;
          UCHAR DensityCode;
        } ScsiInformation;
      } BusSpecificData;
    } TapeInfo;
  } DeviceSpecific;
} DEVICE_MEDIA_INFO, *PDEVICE_MEDIA_INFO;
````

## Members


`DeviceSpecific`



## Remarks
This structure is used by a storage driver to indicate the types of media supported by a device and which type is currently mounted, if any. A driver must provide this information if it might control drives in a media library or changer or if its device might be accessed by the Removable Storage Manager (RSM). 

The driver fills in an array of <b>DEVICE_MEDIA_INFO</b> structures, one for each medium type supported by the device, embedded in a <a href="..\ntddstor\ns-ntddstor-_get_media_types.md">GET_MEDIA_TYPES</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h (include Ntddstor.h, Minitape.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567939">TapeMiniGetMediaTypes</a>



<a href="..\ntddstor\ne-ntddstor-_storage_media_type.md">STORAGE_MEDIA_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DEVICE_MEDIA_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>