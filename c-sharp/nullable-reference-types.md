# Nullable Reference Types

The C# compiler offers an advanced static flow analysis that determines
if a variable might be `null` before dereferencing it. There is a number
of attributes and annotations that provide additional information to the
compiler about variables, parameters and functions, so that it can
correctly predict if a variable might be null in a certain situation.

The feature is disabled by default for existing projects (enabled by
default in new project starting in .NET 6). There are two main ways to
enable it in an existing project:

1. The `Nullable` compiler option, that will enable Nullable reference
	 types project-wide.

2. The `#nullable` directive, that enables Nullable reference types for
	 the rest of the source file where it is located.

See also:

[Nullable reference types | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/csharp/nullable-references)
[Nullable compiler option | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/compiler-options/language#nullable)

