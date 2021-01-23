[![license](https://img.shields.io/github/license/micro-os-plus/platform-stm32f4discovery-xpack)](https://github.com/micro-os-plus/platform-stm32f4discovery-xpack/blob/xpack/LICENSE)

# A source xPack with the STM32F4DISCOVERY board support files

The [STM32F4DISCOVERY](https://www.st.com/en/evaluation-tools/stm32f4discovery.html)
board is a development board from ST MIcroelectronics with
the STM32F407VG MCU.

This project provides the initialization code generated by CubeMX.

## Maintainer info

This page is addressed to developers who plan to include this package
into their own projects.

For maintainer infos, please see the
[README-MAINTAINER](README-MAINTAINER.md) file.

## Easy install

Note: the package will be available from npmjs.com at a later date.

When ready this package will be available as
[`@micro-os-plus/platform-stm32f4discovery`](https://www.npmjs.com/package/@micro-os-plus/platform-stm32f4discovery)
from the `npmjs.com` registry; with [xpm](https://xpack.github.io/xpm/)
available, installing the latest version of the package is quite easy:

```console
$ cd <project>
$ xpm init # Unless a package.json is already present

$ xpm install @micro-os-plus/platform-stm32f4discovery@latest
```

This package is also available from
[GitHub](https://github.com/micro-os-plus/platform-stm32f4discovery-xpack):

```console
$ git clone https://github.com/micro-os-plus/platform-stm32f4discovery-xpack.git platform-stm32f4discovery-xpack.git
```

## Branches

Apart from the unused `master` branch, there are three active branches:

- `xpack`, with the latest stable version
- `xpack-develop`, with the current development version

All development is done in the `xpack-develop` branch, and contributions via
Pull Requests should be directed to this branch.

When new releases are published, the `xpack-develop` branch is merged
into `xpack`.

## User info

This project can be used as-is for simple tests or blinky projects.

It can also be copied into
the user project, the configuration updated, and content regenerated,
at any time.

## Build & integration info

To integrate this package into user projects, consider the following details:

### Source folders

- `stm32cubemx/Core/Src`
- `stm32cubemx/Drivers/STM32F4xx_HAL_Driver/Src`

### Include folders

- `stm32cubemx/Core/Inc`
- `stm32cubemx/Drivers/CMSIS/Device/ST/STM32F4xx/Include`
- `stm32cubemx/Drivers/CMSIS/Include`
- `stm32cubemx/Drivers/STM32F4xx_HAL_Driver/Inc`

The header file to be included in user project is:

```c
#include <stm32f4xx.h>
```

### Preprocessor definitions

- `OS_INCLUDE_MICRO_OS_PLUS_DIAG_TRACE` to enable the `trace_printf()`
  calls in `Error_Handler()` and `assert_failed()`.

### Compiler options

- none required

## Interrupt handlers

The CubeMX configuration explicitly disabled the generation of the
interrupt handlers, such that the more elaborated handlers available
with µOS++ be used.

For a correct integration with the rest of the HAL,
the `SysTick_Handler` should also call some HAL specific functions.

TBD

## Example

TBD

## License

The original content is released under the
[MIT License](https://opensource.org/licenses/MIT), with all rights reserved to
[Liviu Ionescu](https://github.com/ilg-ul).

The HAL code generated by CubeMX is distributed under BSD-3-Clause license.
