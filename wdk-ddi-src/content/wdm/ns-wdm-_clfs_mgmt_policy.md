---
UID: NS:wdm._CLFS_MGMT_POLICY
title: _CLFS_MGMT_POLICY
author: windows-driver-content
description: The CLFS_MGMT_POLICY structure holds a description of a policy for managing a CLFS log.
old-location: kernel\clfs_mgmt_policy.htm
old-project: kernel
ms.assetid: 6765ced9-e21f-4bd9-bb2b-45df1d6dba75
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _CLFS_MGMT_POLICY, *PCLFS_MGMT_POLICY, CLFS_MGMT_POLICY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CLFS_MGMT_POLICY
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.typenames: *PCLFS_MGMT_POLICY, CLFS_MGMT_POLICY
req.product: Windows 10 or later.
---

# _CLFS_MGMT_POLICY structure



## -description
The <b>CLFS_MGMT_POLICY</b> structure holds a description of a policy for managing a CLFS log.



## -syntax

````
typedef struct _CLFS_MGMT_POLICY {
  ULONG                 Version;
  ULONG                 LengthInBytes;
  ULONG                 PolicyFlags;
  CLFS_MGMT_POLICY_TYPE PolicyType;
  union {
    struct {
      ULONG Containers;
    } MaximumSize;
    struct {
      ULONG Containers;
    } MinimumSize;
    struct {
      ULONG SizeInBytes;
    } NewContainerSize;
    struct {
      ULONG AbsoluteGrowthInContainers;
      ULONG RelativeGrowthPercentage;
    } GrowthRate;
    struct {
      ULONG MinimumAvailablePercentage;
      ULONG MinimumAvailableContainers;
    } LogTail;
    struct {
      ULONG Percentage;
    } AutoShrink;
    struct {
      ULONG Enabled;
    } AutoGrow;
    struct {
      USHORT PrefixLengthInBytes;
      WCHAR  PrefixString[1];
    } NewContainerPrefix;
    struct {
      ULONGLONG NextContainerSuffix;
    } NewContainerSuffix;
    struct {
      USHORT ExtensionLengthInBytes;
      WCHAR  ExtensionString[1];
    } NewContainerExtension;
  } PolicyParameters;
} CLFS_MGMT_POLICY, *PCLFS_MGMT_POLICY;
````


## -struct-fields

### -field Version

The version of the <b>CLFS_MGMT_POLICY</b> structure. Set this to <b>CLFS_MGMT_POLICY_VERSION</b>.


### -field LengthInBytes

The length of the <b>CLFS_MGMT_POLICY</b> structure.


### -field PolicyFlags

The flags that apply to this instance of the <b>CLFS_MGMT_POLICY</b> structure. The only flag that has been implemented for this release is <b>LOG_POLICY_OVERWRITE</b>, which indicates that when the policy is installed, it will replace the policy of the same type, if such a policy already exists.


### -field PolicyType

A value of the <a href="..\wdm\ne-wdm-_clfs_mgmt_policy_type.md">CLFS_MGMT_POLICY_TYPE</a> enumeration that supplies the type of this instance of the <b>CLFS_MGMT_POLICY</b> structure.


### -field PolicyParameters

The union that provides the detailed information about this instance of the <b>CLFS_MGMT_POLICY</b> structure.


### -field MaximumSize

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyMaximumSize</b>.


### -field Containers

The maximum number of containers that the log will use.

</dd>
</dl>

### -field MinimumSize

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyMinimumSize</b>.


### -field Containers

The minimum number of containers that the log will use.

</dd>
</dl>

### -field NewContainerSize

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyNewContainerSize</b>.


### -field SizeInBytes

The size of each of the log's containers.

</dd>
</dl>

### -field GrowthRate

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyGrowthRate</b>.


### -field AbsoluteGrowthInContainers

The number of containers that should be added when the size of the log is increased. If the <b>RelativeGrowthPercentage</b> member is nonzero, then <b>AbsoluteGrowthInContainers</b> must be zero.


### -field RelativeGrowthPercentage

The percentage by which the log's size should increase when the log grows, expressed as a number between zero and 100. For example, if the log consisted of 32 containers and <b>RelativeGrowthPercentage</b> was ten, then, when the log needed to grow, it would grow by three (32 * 10 percent, rounded down to the nearest integer) containers. If the <b>AbsoluteGrowthInContainers</b> member is nonzero, then <b>RelativeGrowthPercentage</b> must be zero.

</dd>
</dl>

### -field LogTail

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyLogTail</b>.


### -field MinimumAvailablePercentage

When CLFS management notifies the client to move its log tail, it will specify that the tail be moved to an LSN that leaves at least <b>MinimumAvailablePercentage</b> percent of the log free. If the <b>MinimumAvailableContainers</b> member is nonzero, then <b>MinimumAvailablePercentage</b> must be zero.


### -field MinimumAvailableContainers

When CLFS management notifies the client to move its log tail, it will specify that the tail be moved to an LSN that leaves at least <b>MinimumAvailableContainers</b> containers free. If the <b>MinimumAvailablePercentage</b> member is nonzero, then <b>MinimumAvailableContainers</b> must be zero.

</dd>
</dl>

### -field AutoShrink

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyAutoShrink</b>.


### -field Percentage

When the percentage of free space in the log reaches <b>Percentage</b>, the log will shrink. Percentage is expressed as a number between 0 and 100, so a value of 25 would mean 25 percent.

</dd>
</dl>

### -field AutoGrow

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyAutoGrow</b>.


### -field Enabled

A numeric value that determines whether automatic log growth is enabled. Any nonzero value enables automatic growth.

</dd>
</dl>

### -field NewContainerPrefix

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyNewContainerPrefix</b>.


### -field PrefixLengthInBytes

The length, in bytes, of the <b>PrefixString</b> member.


### -field PrefixString

A wide-character string that contains the full path to the directory where the log's containers reside, as well as a prefix that will be used as part of the file name for each container in the log.

</dd>
</dl>

### -field NewContainerSuffix

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyNewContainerSuffix</b>.


### -field NextContainerSuffix

The number to use as the suffix of the file name for the next container in the log. To form the file name, the number is converted to a string of decimal digits and appended to the prefix string. The number is incremented for the file name of each subsequent container.

</dd>
</dl>

### -field NewContainerExtension

The structure that provides the detailed information about a policy whose <b>PolicyType</b> is <b>ClfsMgmtPolicyNewContainerExtension</b>.


### -field ExtensionLengthInBytes

The length, in bytes, of the <b>ExtensionString</b> member.


### -field ExtensionString

A wide-character string that contains the extension to the file name for each container in the log. Container file names are built using the format [prefix][suffix][.extension]. An extension is optional. The default extension is the empty string.

</dd>
</dl>
</dd>
</dl>

## -remarks
The way a <b>CLFS_MGMT_POLICY</b> structure is interpreted depends on the type of policy that the structure holds.

You can provide <i>policies</i> that specify how the log will be managed. Each policy is an instance of the <b>CLFS_MGMT_POLICY</b> structure, but the structure is interpreted differently depending on the policy type. CLFS uses the information that you provided in the policies to tailor how it manages the log.

When you create a <b>CLFS_MGMT_POLICY</b> structure whose <b>PolicyType</b> is <b>ClfsMgmtPolicyNewContainerPrefix</b>, be sure to allocate enough space to hold the <b>PolicyParameters.NewContainerPrefix.PrefixString</b> string.

You can only install a policy whose policy type specified in the <b>PolicyType</b> value is <b>ClfsMgmtPolicyNewContainerSize</b> before there are any containers in the log. You can change other policies after the log exists.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ne-wdm-_clfs_mgmt_policy_type.md">CLFS_MGMT_POLICY_TYPE</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-clfsmgmtinstallpolicy.md">ClfsMgmtInstallPolicy</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-clfsmgmtquerypolicy.md">ClfsMgmtQueryPolicy</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-clfsmgmtremovepolicy.md">ClfsMgmtRemovePolicy</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CLFS_MGMT_POLICY structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

