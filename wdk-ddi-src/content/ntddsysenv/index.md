---
UID: NA:
---

# Ntddsysenv.h header

## -description

This header is used by Windows kernel. For more information, see
- [Windows kernel](../_kernel/index.md)

Ntddsysenv.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_SYSENV_VALUE structure](ns-ntddsysenv-_sysenv_value.md) | Stores the value of a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_GET_VARIABLE request. |
| [_SYSENV_VARIABLE structure](ns-ntddsysenv-_sysenv_variable.md) | Stores the name a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_GET_VARIABLE request. |
| [_SYSENV_VARIABLE_INFO structure](ns-ntddsysenv-_sysenv_variable_info.md) | Stores the information about a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_QUERY_VARIABLE_INFO request. |
| [_XVARIABLE_NAME structure](ns-ntddsysenv-_xvariable_name.md) | Stores the name of a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_ENUM_VARIABLES request. |
| [_XVARIABLE_NAME_AND_VALUE structure](ns-ntddsysenv-_xvariable_name_and_value.md) | Stores the name and value of a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_ENUM_VARIABLES and IOCTL_SYSENV_SET_VARIABLE requests. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_SYSENV_ENUM_VARIABLES IOCTL](ni-ntddsysenv-ioctl_sysenv_enum_variables.md) | Returns information about system environment variables using SysEnv device. |
| [IOCTL_SYSENV_GET_VARIABLE IOCTL](ni-ntddsysenv-ioctl_sysenv_get_variable.md) | Gets the value of the specified system environment variables using SysEnv device. |
| [IOCTL_SYSENV_QUERY_VARIABLE_INFO IOCTL](ni-ntddsysenv-ioctl_sysenv_query_variable_info.md) | Returns information about system environment variables using SysEnv device. |
| [IOCTL_SYSENV_SET_VARIABLE IOCTL](ni-ntddsysenv-ioctl_sysenv_set_variable.md) | Sets the value of the specified system environment variables using SysEnv device. |
