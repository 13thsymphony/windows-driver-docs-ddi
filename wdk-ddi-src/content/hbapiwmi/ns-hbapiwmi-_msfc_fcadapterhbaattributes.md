---
UID: NS:hbapiwmi._MSFC_FCAdapterHBAAttributes
title: "_MSFC_FCAdapterHBAAttributes"
author: windows-driver-content
description: The MSFC_FCAdapterHBAAttributes structure is used by a WMI provider to expose attribute information associated with a fibre channel adapter.
old-location: storage\msfc_fcadapterhbaattributes.htm
old-project: storage
ms.assetid: 5efe0ede-b55f-499e-9f95-66652cd8a872
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PMSFC_FCAdapterHBAAttributes, MSFC_FCAdapterHBAAttributes, MSFC_FCAdapterHBAAttributes structure [Storage Devices], PMSFC_FCAdapterHBAAttributes, PMSFC_FCAdapterHBAAttributes structure pointer [Storage Devices], _MSFC_FCAdapterHBAAttributes, hbapiwmi/MSFC_FCAdapterHBAAttributes, hbapiwmi/PMSFC_FCAdapterHBAAttributes, storage.msfc_fcadapterhbaattributes, structs-Fibre_07d902b9-2da0-4bca-94ab-db837beff481.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbapiwmi.h
api_name:
-	MSFC_FCAdapterHBAAttributes
product: Windows
targetos: Windows
req.typenames: MSFC_FCAdapterHBAAttributes, *PMSFC_FCAdapterHBAAttributes
---

# _MSFC_FCAdapterHBAAttributes structure
The MSFC_FCAdapterHBAAttributes structure is used by a WMI provider to expose attribute information associated with a fibre channel adapter.

## Syntax
```
typedef struct _MSFC_FCAdapterHBAAttributes {
  ULONGLONG UniqueAdapterId;
  ULONG     HBAStatus;
  UCHAR     NodeWWN[8];
  ULONG     VendorSpecificID;
  ULONG     NumberOfPorts;
  WCHAR     Manufacturer[64 + 1];
  WCHAR     SerialNumber[64 + 1];
  WCHAR     Model[256 + 1];
  WCHAR     ModelDescription[256 + 1];
  WCHAR     NodeSymbolicName[256 + 1];
  WCHAR     HardwareVersion[256 + 1];
  WCHAR     DriverVersion[256 + 1];
  WCHAR     OptionROMVersion[256 + 1];
  WCHAR     FirmwareVersion[256 + 1];
  WCHAR     DriverName[256 + 1];
  WCHAR     MfgDomain[256 + 1];
} *PMSFC_FCAdapterHBAAttributes, MSFC_FCAdapterHBAAttributes;
```

## Members


`UniqueAdapterId`

Indicates the unique adapter ID.

`HBAStatus`

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.

`NodeWWN`

Contains the 64 bit world-wide name that indicates the node name of the HBA. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.

`VendorSpecificID`

Indicates a vendor-specific ID.

`NumberOfPorts`

Indicates the number of ports on the HBA.

`Manufacturer`

Contains an ASCII string that is 64 bytes or fewer in length and that identifies the name of the manufacturer of the HBA.

`SerialNumber`

Contains an ASCII string that is 64 bytes or fewer in length and that identifies the serial number of the HBA.

`Model`

Contains an ASCII string that is 256 bytes or fewer in length and that identifies the vendor-specific name of the HBA model.

`ModelDescription`

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the model description.

`NodeSymbolicName`

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the symbolic name for the fibre channel node.

`HardwareVersion`

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific hardware revision level of the HBA.

`DriverVersion`

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific version of the HBA miniport driver.

`OptionROMVersion`

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific option ROM or BIOS version of the HBA.

`FirmwareVersion`

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific firmware version of the HBA.

`DriverName`

Contains an ASCII string that is 256 bytes or fewer in length and that indicates the file name for the driver binary file.

`MfgDomain`

Contains the name of the HBA manufacturer.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562497">MSFC_FCAdapterHBAAttributes WMI Class</a>