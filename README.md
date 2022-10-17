
# Notes

`myconsole.csproj` and `nuget.config` contain paths to my checkout of dotnet/runtime.

# Versions

dotnet/runtime: 960e4d723c27a5407dc691d06e546bc455a9c4a5

Reproduces on linux-arm64 and osx-arm64.

# Stack trace

```
 at ILCompiler.DependencyAnalysis.ARM64.ARM64Emitter.EmitLDR(Register regDst, Register regSrc, Int32 offset) in /Users/austin/src/runtime/src/coreclr/tools/Common/Compiler/DependencyAnalysis/Target_ARM64/ARM64Emitter.cs:line 66
   at ILCompiler.DependencyAnalysis.ReadyToRunHelperNode.EmitCode(NodeFactory factory, ARM64Emitter& encoder, Boolean relocsOnly) in /Users/austin/src/runtime/src/coreclr/tools/aot/ILCompiler.Compiler/Compiler/DependencyAnalysis/Target_ARM64/ARM64ReadyToRunHelperNode.cs:line 38
   at ILCompiler.DependencyAnalysis.AssemblyStubNode.GetData(NodeFactory factory, Boolean relocsOnly) in /Users/austin/src/runtime/src/coreclr/tools/Common/Compiler/DependencyAnalysis/AssemblyStubNode.cs:line 66
   at ILCompiler.DependencyAnalysis.ObjectWriter.EmitObject(String objectFilePath, IReadOnlyCollection`1 nodes, NodeFactory factory, ObjectWritingOptions options, IObjectDumper dumper, Logger logger) in /Users/austin/src/runtime/src/coreclr/tools/aot/ILCompiler.Compiler/Compiler/DependencyAnalysis/ObjectWriter.cs:line 988
   at ILCompiler.RyuJitCompilation.CompileInternal(String outputFile, ObjectDumper dumper) in /Users/austin/src/runtime/src/coreclr/tools/aot/ILCompiler.RyuJit/Compiler/RyuJitCompilation.cs:line 103
   at ILCompiler.Compilation.ILCompiler.ICompilation.Compile(String outputFile, ObjectDumper dumper) in /Users/austin/src/runtime/src/coreclr/tools/aot/ILCompiler.Compiler/Compiler/Compilation.cs:line 524
   at ILCompiler.Program.Run() in /Users/austin/src/runtime/src/coreclr/tools/aot/ILCompiler/Program.cs:line 487
```
