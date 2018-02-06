---
UID: NE:ntddmmc._FEATURE_PROFILE_TYPE
title: "_FEATURE_PROFILE_TYPE"
author: windows-driver-content
description: The FEATURE_PROFILE_TYPE enumeration provides a list of the profile names that are defined by the SCSI Multimedia - 4 (MMC-4) specification.
old-location: storage\feature_profile_type.htm
old-project: storage
ms.assetid: 60cce78f-1025-41a7-861d-150ef28376cb
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddmmc/ProfileDvdRWSequential, ntddmmc/ProfileHDDVDRDualLayer, ProfileAS_MO, ntddmmc/ProfileDDCdRewritable, ProfileHDDVDRom, ProfileNonRemovableDisk, ntddmmc/ProfileDvdRom, ProfileDvdPlusR, ProfileDvdPlusRWDualLayer, ProfileHDDVDRDualLayer, PFEATURE_PROFILE_TYPE enumeration pointer [Storage Devices], ntddmmc/ProfileDvdRam, ntddmmc/ProfileCdRecordable, ntddmmc/PFEATURE_PROFILE_TYPE, ProfileBDRewritable, ntddmmc/ProfileBDRSequentialWritable, FEATURE_PROFILE_TYPE enumeration [Storage Devices], ProfileMOErasable, ntddmmc/ProfileMOWriteOnce, ProfileCdRewritable, ProfileDvdPlusRDualLayer, ProfileRemovableDisk, ProfileDvdRWSequential, ProfileDDCdRecordable, ntddmmc/ProfileDDCdRecordable, ntddmmc/ProfileBDRom, ntddmmc/ProfileInvalid, ProfileHDDVDRam, ProfileMOWriteOnce, ntddmmc/ProfileRemovableDisk, storage.feature_profile_type, ProfileDvdRam, ProfileDvdRom, ProfileDDCdRewritable, ntddmmc/ProfileCdrom, ntddmmc/ProfileDvdPlusRWDualLayer, ProfileBDRSequentialWritable, ntddmmc/ProfileHDDVDRewritable, structs-CD-ROM_89bf20da-a096-4f37-ab24-219533578d34.xml, ntddmmc/ProfileDvdRewritable, ntddmmc/ProfileDDCdrom, ntddmmc/ProfileHDDVDRecordable, ProfileInvalid, ntddmmc/ProfileAS_MO, ProfileBDRRandomWritable, ntddmmc/ProfileHDDVDRam, PFEATURE_PROFILE_TYPE, ProfileHDDVDRewritable, ntddmmc/ProfileBDRewritable, ProfileDDCdrom, ProfileHDDVDRecordable, ProfileDvdDashRLayerJump, ntddmmc/ProfileNonRemovableDisk, ProfileHDDVDRWDualLayer, ntddmmc/ProfileDvdPlusR, ntddmmc/ProfileNonStandard, ntddmmc/ProfileCdRewritable, ntddmmc/ProfileHDDVDRom, ntddmmc/ProfileDvdDashRDualLayer, ProfileDvdPlusRW, _FEATURE_PROFILE_TYPE, ntddmmc/ProfileDvdDashRLayerJump, ntddmmc/ProfileBDRRandomWritable, ntddmmc/FEATURE_PROFILE_TYPE, ProfileDvdDashRDualLayer, ntddmmc/ProfileDvdPlusRW, ProfileDvdRecordable, ProfileNonStandard, FEATURE_PROFILE_TYPE, ntddmmc/ProfileHDDVDRWDualLayer, ProfileCdRecordable, ntddmmc/ProfileDvdRecordable, ntddmmc/ProfileDvdPlusRDualLayer, ProfileBDRom, ProfileDvdRewritable, ntddmmc/ProfileMOErasable, ProfileCdrom, *PFEATURE_PROFILE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddmmc.h
req.include-header: Ntddcdrm.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddmmc.h
apiname:
-	FEATURE_PROFILE_TYPE
product: Windows
targetos: Windows
req.typenames: "*PFEATURE_PROFILE_TYPE, FEATURE_PROFILE_TYPE"
---

# _FEATURE_PROFILE_TYPE Enumeration
The FEATURE_PROFILE_TYPE enumeration provides a list of the profile names that are defined by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification.

## Syntax
````
typedef enum _FEATURE_PROFILE_TYPE { 
  ProfileInvalid                = 0x0000,
  ProfileNonRemovableDisk       = 0x0001,
  ProfileRemovableDisk          = 0x0002,
  ProfileMOErasable             = 0x0003,
  ProfileMOWriteOnce            = 0x0004,
  ProfileAS_MO                  = 0x0005,
  ProfileCdrom                  = 0x0008,
  ProfileCdRecordable           = 0x0009,
  ProfileCdRewritable           = 0x000a,
  ProfileDvdRom                 = 0x0010,
  ProfileDvdRecordable          = 0x0011,
  ProfileDvdRam                 = 0x0012,
  ProfileDvdRewritable          = 0x0013,
  ProfileDvdRWSequential        = 0x0014,
  ProfileDvdDashRDualLayer      = 0x0015,
  ProfileDvdDashRLayerJump      = 0x0016,
  ProfileDvdPlusRW              = 0x001A,
  ProfileDvdPlusR               = 0x001B,
  ProfileDDCdrom                = 0x0020,
  ProfileDDCdRecordable         = 0x0021,
  ProfileDDCdRewritable         = 0x0022,
  ProfileDvdPlusRWDualLayer     = 0x002A,
  ProfileDvdPlusRDualLayer      = 0x002B,
  ProfileBDRom                  = 0x0040,
  ProfileBDRSequentialWritable  = 0x0041,
  ProfileBDRRandomWritable      = 0x0042,
  ProfileBDRewritable           = 0x0043,
  ProfileHDDVDRom               = 0x0050,
  ProfileHDDVDRecordable        = 0x0051,
  ProfileHDDVDRam               = 0x0052,
  ProfileHDDVDRewritable        = 0x0053,
  ProfileHDDVDRDualLayer        = 0x0058,
  ProfileHDDVDRWDualLayer       = 0x005A,
  ProfileNonStandard            = 0xffff
} FEATURE_PROFILE_TYPE, *PFEATURE_PROFILE_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>ProfileAS_MO</td>
                    <td>Indicates the profile named "AS-MO" by the <i>MMC-3</i> specification. This profile is used with devices that implement Advance Storage technology and manage magneto-optical media.</td>
                </tr>
            
                <tr>
                    <td>ProfileBDRewritable</td>
                    <td>Reserved 0x0044 - 0x004F</td>
                </tr>
            
                <tr>
                    <td>ProfileBDRom</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>ProfileBDRRandomWritable</td>
                    <td>BD-R 'RRM'</td>
                </tr>
            
                <tr>
                    <td>ProfileBDRSequentialWritable</td>
                    <td>BD-R 'SRM'</td>
                </tr>
            
                <tr>
                    <td>ProfileCdRecordable</td>
                    <td>Indicates the profile named "CD-R" by the <i>MMC-3</i> specification. This profile is used with devices that manage write-once compact disc media.</td>
                </tr>
            
                <tr>
                    <td>ProfileCdRewritable</td>
                    <td>Indicates the profile named "CD-RW" by the <i>MMC-3</i> specification. This profile is used with devices that manage rewritable compact disc media.</td>
                </tr>
            
                <tr>
                    <td>ProfileCdrom</td>
                    <td>Indicates the profile named "CD-ROM" by the <i>MMC-3</i> specification. This profile is used with devices that manage read-only compact disc media.</td>
                </tr>
            
                <tr>
                    <td>ProfileDDCdRecordable</td>
                    <td>Indicates the profile named "DDCD-R" by the <i>MMC-3</i> specification. This profile is used with devices that can read "DDCD-R specific structure." For a full list of the features supported with this profile, see the <i>MMC-3</i> specification.</td>
                </tr>
            
                <tr>
                    <td>ProfileDDCdRewritable</td>
                    <td>Indicates the profile named "DDCD-RW" by the <i>MMC-3</i> specification. This profile is used with devices that can read "DDCD-RW specific structure." For a full list of the features supported with this profile, see the <i>MMC-3</i> specification.</td>
                </tr>
            
                <tr>
                    <td>ProfileDDCdrom</td>
                    <td>Indicates the profile named "DDCD-ROM" by the <i>MMC-3</i> specification. This profile is used with devices that can read "DDCD specific structure." For a full list of the features supported with this profile, see the <i>MMC-3</i> specification.</td>
                </tr>
            
                <tr>
                    <td>ProfileDvdDashRDualLayer</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>ProfileDvdDashRLayerJump</td>
                    <td>Reserved 0x0017 - 0x0019</td>
                </tr>
            
                <tr>
                    <td>ProfileDvdPlusR</td>
                    <td>Reserved 0x001C - 001F</td>
                </tr>
            
                <tr>
                    <td>ProfileDvdPlusRDualLayer</td>
                    <td>Reserved 0x002C - 0x003F</td>
                </tr>
            
                <tr>
                    <td>ProfileDvdPlusRW</td>
                    <td>Indicates the profile named "DVD+RW" by the <i>MMC-3</i> specification. This profile is used with devices that implement a series of features required to manage DVD media that is both readable and writable. For a full list of the features supported with this profile, see the <i>MMC-3</i> specification.</td>
                </tr>
            
                <tr>
                    <td>ProfileDvdPlusRWDualLayer</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>ProfileDvdRam</td>
                    <td>Indicates the profile named "DVD-RAM or DVD+RW" by the <i>MMC-3</i> specification. This profile is used with devices that manage rewritable DVD media.</td>
                </tr>
            
                <tr>
                    <td>ProfileDvdRecordable</td>
                    <td>Indicates the profile named "DVD-R" by the <i>MMC-3</i> specification. This profile is used with devices that manage write-once DVD media and operate in sequential recording mode.</td>
                </tr>
            
                <tr>
                    <td>ProfileDvdRewritable</td>
                    <td>Indicates the profile named "DVD-RW Restricted Overwrite" by the <i>MMC-3</i> specification. This profile is used with devices that manage rerecordable DVD media and operate in packet-writing mode.</td>
                </tr>
            
                <tr>
                    <td>ProfileDvdRom</td>
                    <td>Indicates the profile named "DVD-ROM" by the <i>MMC-3</i> specification. This profile is used with devices that manage read-only DVD media.</td>
                </tr>
            
                <tr>
                    <td>ProfileDvdRWSequential</td>
                    <td>Indicates the profile named "DVD-RW Sequential Recording" by the <i>MMC-3</i> specification. This profile is used with devices that implement a series of features associated with sequential recording, such as the features "Incremental Streaming Writable" and "Real-Time Streaming". For a full list of the features supported with this profile, see the <i>MMC-3</i> specification.</td>
                </tr>
            
                <tr>
                    <td>ProfileHDDVDRam</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>ProfileHDDVDRDualLayer</td>
                    <td>Reserved 0x0059 - 0x0059</td>
                </tr>
            
                <tr>
                    <td>ProfileHDDVDRecordable</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>ProfileHDDVDRewritable</td>
                    <td>Reserved 0x0054 - 0x0057</td>
                </tr>
            
                <tr>
                    <td>ProfileHDDVDRom</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>ProfileHDDVDRWDualLayer</td>
                    <td>Reserved 0x005B - 0xfffe</td>
                </tr>
            
                <tr>
                    <td>ProfileInvalid</td>
                    <td>Does not indicate a valid profile.</td>
                </tr>
            
                <tr>
                    <td>ProfileMOErasable</td>
                    <td>Indicates the profile named "MO Erasable" by the <i>MMC-3</i> specification. This profile is used with devices that manage magneto-optical media and that have a sector-erase capability.</td>
                </tr>
            
                <tr>
                    <td>ProfileMOWriteOnce</td>
                    <td>Indicates the profile named "MO Write Once" by the <i>MMC-3</i> specification. This profile is used with devices that manage magneto-optical write-once media.</td>
                </tr>
            
                <tr>
                    <td>ProfileNonRemovableDisk</td>
                    <td>Indicates the profile named "Nonremovable disk" by the <i>SCSI-3 Multimedia (MMC-3)</i> specification. This profile is used with devices that manage rewritable media and are capable of changing behavior.</td>
                </tr>
            
                <tr>
                    <td>ProfileNonStandard</td>
                    <td>Indicates that the device does not conform to any profile.</td>
                </tr>
            
                <tr>
                    <td>ProfileRemovableDisk</td>
                    <td>Indicates the profile named "Removable disk" by the <i>MMC-3</i> specification. This profile is used with devices that manage rewritable, removable media.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

    ## See Also

        <a href="..\ntddmmc\ns-ntddmmc-_feature_data_profile_list.md">FEATURE_DATA_PROFILE_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_PROFILE_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>