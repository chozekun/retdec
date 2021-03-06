# Changelog

# dev

* New Feature: Added a new tool: `retdec-getsig`. It can be used for creating signatures of packers, compilers, and other tools.
* Enhancement: Tool `retdec-macho-extractor` can now extract objects from non-archive Mach-O universal binaries ([#125](https://github.com/avast-tl/retdec/issues/125)).
* Enhancement: References to ticket numbers from our internal issue tracking system were replaced by short descriptions in the `retdec-regression-tests` repository ([retdec-regression-tests #1](https://github.com/avast-tl/retdec-regression-tests/issues/1)).
* Enhancement: Added a missing license for the `retdec-support` repository ([retdec-support #1](https://github.com/avast-tl/retdec-support/issues/1)).
* Enhancement: Better detection of tools: new signatures and heuristics. YARA signatures are compiled now.
* Enhancement: Added Travis and Appveyor continuous integration builds ([#2](https://github.com/avast-tl/retdec/issues/2)).
* Enhancement: Build with `-std=c++14` instead of `-std=gnu++14` with GCC on Linux ([#76](https://github.com/avast-tl/retdec/issues/76)).
* Enhancement: Speeded up build by skipping compilation of unnecessary dependencies (e.g. unused LLVM libraries, tools, and examples).
* Enhancement: OpenSSL is now automatically built only if it is not found in your system.
* Enhancement: Added support for a system-wide installation ([#94](https://github.com/avast-tl/retdec/issues/94)).
* Enhancement: Prefixed all the installed binaries and scripts with `retdec-` ([#70](https://github.com/avast-tl/retdec/issues/70)). Also, some tools were renamed to make their names more uniform.
* Enhancement: Got rid of all git submodules ([#92](https://github.com/avast-tl/retdec/issues/92), [#93](https://github.com/avast-tl/retdec/issues/93)). Moved sources of all RetDec-related repositories to this main repository. Third-party dependencies are downloaded and built via CMake's external projects. This allows us to have e.g. only a single copy of LLVM ([#14](https://github.com/avast-tl/retdec/issues/14)) and not require a recursive clone ([#48](https://github.com/avast-tl/retdec/issues/48), [#68](https://github.com/avast-tl/retdec/issues/68), [#72](https://github.com/avast-tl/retdec/issues/72)).
* Enhancement: Set a proper `rpath` during installation on Linux and macOS ([#77](https://github.com/avast-tl/retdec/issues/77), [#100](https://github.com/avast-tl/retdec/issues/100)). This allows us to move the installation directory after the installation into another location.
* Enhancement: Added community support for building and running RetDec inside Docker ([#60](https://github.com/avast-tl/retdec/pull/60)).
* Enhancement: Decrease the default timeout when downloading the support package during installation ([#6](https://github.com/avast-tl/retdec/pull/6)).
* Enhancement: Any shell can be used to install the decompiler, not just Bash.
* Enhancement: Added unofficial support for macOS build ([#7](https://github.com/avast-tl/retdec/issues/7)).
* Enhancement: Allow 32b versions of `bin2llvmir` and `llvmir2hll` on Windows access more memory ([#7](https://github.com/avast-tl/retdec/issues/73)).
* Enhancement: Added method in `loader::Image` to obtain segment content as raw data pointer.
* Fix: Non-printable characters in ELF .dynamic section output are now replaced with hexadecimal codes. ([#82](https://github.com/avast-tl/retdec/issues/82)).
* Fix: Fix for several segmentation faults in ELF parsing module ([#89](https://github.com/avast-tl/retdec/issues/89)).
* Fix: Added a workaround for a GCC 5 compilation bug ([#231](https://github.com/avast-tl/retdec/issues/231)).
* Fix: Fix LLVM (and therefore RetDec) build on systems with architecture other than x86 ([llvm #3](https://github.com/avast-tl/llvm/issues/3)).
* Fix: Valid Mach-O x64 relocations are no longer ignored.
* Fix: Only a single copy of LLVM (and all other components) is kept ([#14](https://github.com/avast-tl/retdec/issues/14)).
* Fix: RetDec works even if it is installed to a directory which have whitespaces in its path.
* Fix: Reduced the length of build paths to external projects ([#61](https://github.com/avast-tl/retdec/issues/61)).
* Fix: Build of `googletest` with VS 2017 ([#55](https://github.com/avast-tl/retdec/issues/55)).
* Fix: Build of `retdec-config` when two different compilers are employed ([#52](https://github.com/avast-tl/retdec/issues/52)).
* Fix: Build of the `llvm` submodule with VS 2017 when DIA SDK is installed ([#61](https://github.com/avast-tl/retdec/issues/61)).
* Fix: Ordering of compiler detections ([#39](https://github.com/avast-tl/retdec/issues/39)).
* Fix: Remove duplicate `lib` prefix when installing [libdwarf](https://github.com/avast-tl/libdwarf) libraries ([#31](https://github.com/avast-tl/retdec/issues/31)).
* Fix: When installing the decompiler, do not remove the entire `share` directory ([#12](https://github.com/avast-tl/retdec/issues/12)).
* Fix: Improve OS type detection when installing the decompiler.
* Fix: Remove useless OS type detection when running decompilations ([#10](https://github.com/avast-tl/retdec/issues/10)).
* Fix: Filesystem path in utils now returns correct information when it is appended with another path.

# v3.0 (2017-12-13)

Initial public release.
