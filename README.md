# Binary Compatibility Checker

This project implements a binary compatibility checker for .NET assemblies. The goal of this project is to automate the
process of identifying binary- and source-breaking changes between releases of a .NET library. Libraries with string
compatibility policies will eventually be able to incorporate this check in the unit tests for the library. The checker
will download a declared previous release of the library from NuGet (or potentially from another source), and verify
that the latest build of the library is compatible with the binary interfaces defined by the earlier release.

This library may also feature support for higher levels of compatibility, such as warning users if new overloads of a
method could result in an `AmbiguousMatchException` for users who didn't specify a complete signature when using
reflection.

Diagnostics produced by this checker will be categorized by their likely impact on consumers, and by whether the change
constitutes a binary- or source-level breaking change. At this time, there are no plans to implement detection or
reporting for changes in runtime semantics.
