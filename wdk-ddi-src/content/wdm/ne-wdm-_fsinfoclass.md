---
UID: NE:wdm._FSINFOCLASS
title: "_FSINFOCLASS"
author: windows-driver-content
description: The FS_INFORMATION_CLASS enumeration contains the information class constants that specify what type of information structure is present for a set or a query operation.
old-location: ifsk\fs_information_class.htm
old-project: ifsk
ms.assetid: 8A8F938D-8F6B-47E0-963F-8E8B14033802
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFS_INFORMATION_CLASS, FS_INFORMATION_CLASS, FS_INFORMATION_CLASS enumeration [Installable File System Drivers], FileFsAttributeInformation, FileFsControlInformation, FileFsDeviceInformation, FileFsDriverPathInformation, FileFsFullSizeInformation, FileFsLabelInformation, FileFsObjectIdInformation, FileFsSectorSizeInformation, FileFsSizeInformation, FileFsVolumeFlagsInformation, FileFsVolumeInformation, _FSINFOCLASS, ifsk.fs_information_class, wdm/FS_INFORMATION_CLASS, wdm/FileFsAttributeInformation, wdm/FileFsControlInformation, wdm/FileFsDeviceInformation, wdm/FileFsDriverPathInformation, wdm/FileFsFullSizeInformation, wdm/FileFsLabelInformation, wdm/FileFsObjectIdInformation, wdm/FileFsSectorSizeInformation, wdm/FileFsSizeInformation, wdm/FileFsVolumeFlagsInformation, wdm/FileFsVolumeInformation"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	FS_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: FS_INFORMATION_CLASS, *PFS_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# _FSINFOCLASS Enumeration
The FS_INFORMATION_CLASS enumeration contains the information class constants that specify what type of information structure is present for a set or a query operation.

## Syntax
````
typedef enum  { 
  FileFsVolumeInformation       = 1,
  FileFsLabelInformation        = 2,
  FileFsSizeInformation         = 3,
  FileFsDeviceInformation       = 4,
  FileFsAttributeInformation    = 5,
  FileFsControlInformation      = 6,
  FileFsFullSizeInformation     = 7,
  FileFsObjectIdInformation     = 8,
  FileFsDriverPathInformation   = 9,
  FileFsVolumeFlagsInformation  = 10,
  FileFsSectorSizeInformation   = 11
} FS_INFORMATION_CLASS;
````

## Constants

<table>
            
                <tr>
                    <td>FileFsAttributeInformation</td>
                    <td>Return a <a href="..\ntifs\ns-ntifs-_file_fs_attribute_information.md">FILE_FS_ATTRIBUTE_INFORMATION</a> structure that contains attribute information about the file system responsible for the volume.</td>
                </tr>
            
                <tr>
                    <td>FileFsControlInformation</td>
                    <td>Return a <a href="..\ntifs\ns-ntifs-_file_fs_control_information.md">FILE_FS_CONTROL_INFORMATION</a> structure that contains file system control information about the volume.</td>
                </tr>
            
                <tr>
                    <td>FileFsDataCopyInformation</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>FileFsDeviceInformation</td>
                    <td>Return a <a href="..\wdm\ns-wdm-_file_fs_device_information.md">FILE_FS_DEVICE_INFORMATION</a> structure that contains device information for the volume.</td>
                </tr>
            
                <tr>
                    <td>FileFsDriverPathInformation</td>
                    <td>Return a <a href="..\ntifs\ns-ntifs-_file_fs_driver_path_information.md">FILE_FS_DRIVER_PATH_INFORMATION</a> structure that contains information about whether a specified driver is in the I/O path for the volume. The originator of the IRP_MJ_QUERY_VOLUME_INFORMATION request must store the name of the driver into the FILE_FS_DRIVER_PATH_INFORMATION structure before sending the IRP to the file system volume device stack.</td>
                </tr>
            
                <tr>
                    <td>FileFsFullSizeInformation</td>
                    <td>Return a <a href="..\ntddk\ns-ntddk-_file_fs_full_size_information.md">FILE_FS_FULL_SIZE_INFORMATION</a> structure that contains information about the total amount of space available on the volume.</td>
                </tr>
            
                <tr>
                    <td>FileFsLabelInformation</td>
                    <td>Use a <a href="..\ntddk\ns-ntddk-_file_fs_label_information.md">FILE_FS_LABEL_INFORMATION</a> structure to set information a volume label.</td>
                </tr>
            
                <tr>
                    <td>FileFsMaximumInformation</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>FileFsMetadataSizeInformation</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>FileFsObjectIdInformation</td>
                    <td>Return a <a href="..\ntddk\ns-ntddk-_file_fs_objectid_information.md">FILE_FS_OBJECTID_INFORMATION</a> structure that contains file-system-specific object ID information for the volume. Note that this is not the same as the (GUID-based) unique volume name that is assigned by the operating system.</td>
                </tr>
            
                <tr>
                    <td>FileFsSectorSizeInformation</td>
                    <td>Return a <a href="..\ntifs\ns-ntifs-_file_fs_driver_path_information.md">FILE_FS_SECTOR_SIZE_INFORMATION</a> structure that contains information about the physical and logical sector sizes of a volume.</td>
                </tr>
            
                <tr>
                    <td>FileFsSizeInformation</td>
                    <td>Return a <a href="..\ntddk\ns-ntddk-_file_fs_size_information.md">FILE_FS_SIZE_INFORMATION</a> structure containing information about the amount of space on the volume that is available to the user that is associated with the calling thread.</td>
                </tr>
            
                <tr>
                    <td>FileFsVolumeFlagsInformation</td>
                    <td>Use a <b>FILE_FS_VOLUME_FLAGS_INFORMATION</b> structure to set the flags for a volume.</td>
                </tr>
            
                <tr>
                    <td>FileFsVolumeInformation</td>
                    <td>Return a <a href="..\ntddk\ns-ntddk-_file_fs_volume_information.md">FILE_FS_VOLUME_INFORMATION</a> structure that contains information about the volume such as the volume label, serial number, and creation time.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h |