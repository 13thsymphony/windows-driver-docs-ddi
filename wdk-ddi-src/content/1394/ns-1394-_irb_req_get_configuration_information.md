---
UID : NS:1394._IRB_REQ_GET_CONFIGURATION_INFORMATION
title : _IRB_REQ_GET_CONFIGURATION_INFORMATION
author : windows-driver-content
description : This structure contains the fields necessary for the 1394 bus driver to carry out a GetConfigurationInformation request.
old-location : ieee\irb_req_get_configuration_information.htm
old-project : IEEE
ms.assetid : 639B72C4-F99D-4983-8539-00A93398465F
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _IRB_REQ_GET_CONFIGURATION_INFORMATION, IRB_REQ_GET_CONFIGURATION_INFORMATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : 1394.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IRB_REQ_GET_CONFIGURATION_INFORMATION
req.alt-loc : 1394.h
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
req.typenames : IRB_REQ_GET_CONFIGURATION_INFORMATION
---

# _IRB_REQ_GET_CONFIGURATION_INFORMATION structure
This structure contains the fields necessary for the 1394 bus driver to carry out a GetConfigurationInformation request.

## Syntax
````
typedef struct _IRB_REQ_GET_CONFIGURATION_INFORMATION {
  PCONFIG_ROM   ConfigRom;
  ULONG         UnitDirectoryBufferSize;
  PVOID         UnitDirectory;
  IO_ADDRESS    UnitDirectoryLocation;
  ULONG         UnitDependentDirectoryBufferSize;
  PVOID         UnitDependentDirectory;
  IO_ADDRESS    UnitDependentDirectoryLocation;
  ULONG         VendorLeafBufferSize;
  PTEXTUAL_LEAF VendorLeaf;
  ULONG         ModelLeafBufferSize;
  PTEXTUAL_LEAF ModelLeaf;
} IRB_REQ_GET_CONFIGURATION_INFORMATION;
````

## Members

        
            `ConfigRom`

            Points to the buffer that the bus driver uses to store a copy of the device's configuration ROM. The configuration ROM is defined by the <i>IEEE 1394-1995 Specification</i>
        
            `ModelLeaf`

            Points to a buffer to receive the model leaf TEXTUAL_LEAF structure, which describes the device model type.
        
            `ModelLeafBufferSize`

            Specifies the size of the buffer pointed to by <b>ModelLeaf</b> member of <b>u.GetConfigurationInformation</b>. On completion, the bus driver fills in this member with the minimum of the buffer size passed in and the number of bytes of data that were actually available. If the <b>UnitDirectoryBufferSize</b>, <b>UnitDependentDirectoryBufferSize</b>, <b>VendorLeafBufferSize</b>, and <b>ModelLeafBufferSize</b> members of <b>u.GetConfigurationInformation</b> are all zero, the bus driver fills in this member with the minimum buffer size needed to hold all the information.
        
            `UnitDependentDirectory`

            Points to a buffer that receives the unit dependent directory, as defined by the <i>IEEE 1394-1995 Specification</i>. See the <i>IEEE 1394-1995 Specification</i> for a description of the internals of the unit directory.
        
            `UnitDependentDirectoryBufferSize`

            Specifies the size of the buffer pointed to by <b>UnitDependentDirectory</b> member of <b>u.GetConfigurationInformation</b>. On completion, the bus driver fills in this member with the minimum of the buffer size passed in and the number of bytes of data that were actually available. If the <b>UnitDirectoryBufferSize</b>, <b>UnitDependentDirectoryBufferSize</b>, <b>VendorLeafBufferSize</b>, and <b>ModelLeafBufferSize</b> members of <b>u.GetConfigurationInformation</b> are all zero, the bus driver fills in this member with the minimum buffer size needed to hold all the information.
        
            `UnitDependentDirectoryLocation`

            The Unit Dependent Directory location for this device.  Only the
    lower 48 bits are valid in this <b>IO_ADDRESS</b>.
        
            `UnitDirectory`

            Points to where the bus driver returns the unit directory. See the <i>IEEE 1394-1995 Specification</i> for a description of the internals of the unit directory.
        
            `UnitDirectoryBufferSize`

            Specifies the size, in bytes, of the buffer pointed to by the <b>UnitDirectory</b> member of <b>u.GetConfigurationInformation</b>. On completion, the bus driver fills in this member with the minimum of the buffer size passed in and the number of bytes of data that were actually available. If the <b>UnitDirectoryBufferSize</b>, <b>UnitDependentDirectoryBufferSize</b>, <b>VendorLeafBufferSize</b>, and <b>ModelLeafBufferSize</b> members of <b>u.GetConfigurationInformation</b> are all zero, the bus driver fills in this member with the minimum buffer size needed to hold all the available information.
        
            `UnitDirectoryLocation`

            Specifies the starting location of the unit directory.
        
            `VendorLeaf`

            Points to a buffer to receive the vendor leaf TEXTUAL_LEAF structure, which describes the device vendor.
        
            `VendorLeafBufferSize`

            Specifies the size of the buffer pointed to by <b>VendorLeaf</b> member of <b>u.GetConfigurationInformation</b>. On completion, the bus driver fills in this member with the minimum of the buffer size passed in and the number of bytes of data that were actually available. If the <b>UnitDirectoryBufferSize</b>, <b>UnitDependentDirectoryBufferSize</b>, <b>VendorLeafBufferSize</b>, and <b>ModelLeafBufferSize</b> members of <b>u.GetConfigurationInformation</b> are all zero, the bus driver fills in this member with the minimum buffer size needed to hold all the information.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | 1394.h |