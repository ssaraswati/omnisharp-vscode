## C# for Visual Studio Code (powered by OmniSharp)

Welcome to the C# extension for Visual Studio Code! This extension provides the following features inside VS Code:

* Lightweight development tools for [.NET Core](https://dotnet.github.io).
* Great C# editing support, including Syntax Highlighting, IntelliSense, Go to Definition, Find All References, etc.
* Debugging support for .NET Core (CoreCLR). NOTE: Mono debugging is not supported. Desktop CLR debugging has [limited support](https://github.com/OmniSharp/omnisharp-vscode/wiki/Desktop-.NET-Framework).
* Support for project.json and csproj projects on Windows, macOS and Linux.

The C# extension is powered by [OmniSharp](https://github.com/OmniSharp/omnisharp-roslyn).

### Get Started Writing C# in VS Code

* [Documentation](https://code.visualstudio.com/docs/languages/csharp)
* [Video Tutorial compiling with .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-Csharp-NET-Core-Windows)

## Announcements

### Planned removal of the included Mono & MSBuild Tools

In the future .NET Framework builds of OmniSharp will not ship with Mono or the MSBuild tooling (See announcement [omnisharp-roslyn#2339](https://github.com/OmniSharp/omnisharp-roslyn/issues/2339)). To ensure that the C# extension remains usable out of the box for .NET SDK projects, we will be changing the default value of `omnisharp.useModernNet` to `true`.

See issue [#5120](https://github.com/OmniSharp/omnisharp-vscode/issues/5120) for more details.

### Using .NET 6 builds of OmniSharp

Starting with C# extension version 1.24.0, there is now an option to use build of OmniSharp that runs on the .NET 6 SDK. This build requires that the .NET 6 SDK be installed and does not use Visual Studio MSBuild tools or Mono. It only supports newer SDK-style projects that are buildable with `dotnet build`. Unity projects and other Full Framework projects are not supported.

To use the .NET 6 build, set `omnisharp.useModernNet` to `true` in your VS Code settings and restart OmniSharp.

### Note about using .NET Core 3.1.4xx SDKs

The .NET 3.1.4xx SDKs require version 16.7 of MSBuild.

For MacOS and Linux users who have Mono installed, this means you will need to set `omnisharp.useGlobalMono` to `never` until a version of Mono ships with MSBuild 16.7.

You can also use the .NET 6 build of OmniSharp which runs on the .NET 6 SDK. See instructions above.

### Note about using .NET 5 SDKs

The .NET 5 SDK requires version 16.8 of MSBuild.

For Windows users who have Visual Studio installed, this means you will need to be on the latest Visual Studio 16.8 Preview.

For MacOS and Linux users who have Mono installed, this means you will need to set `omnisharp.useGlobalMono` to `never` until a version of Mono ships with MSBuild 16.8.

You can also use the .NET 6 build of OmniSharp which runs on the .NET 6 SDK. See instructions above.

### Note about using .NET 6 SDKs

The .NET 6 SDK requires version 16.10 of MSBuild.

For Windows users who have Visual Studio installed, this means you will need to have Visual Studio 16.11 or newer installed.

For MacOS and Linux users who have Mono installed, this means you will need to set `omnisharp.useGlobalMono` to `never` until a version of Mono ships with MSBuild 16.10.

You can also use the .NET 6 build of OmniSharp which runs on the .NET 6 SDK. See instructions above.

## What's new in 1.24.4
* Remove inlayHints from diff view (PR: [#5151](https://github.com/OmniSharp/omnisharp-vscode/pull/5151))
* Quote arguments containing spaces when launching OmniSharp ([#5150](https://github.com/OmniSharp/omnisharp-vscode/issues/5150), PR: [#5154](https://github.com/OmniSharp/omnisharp-vscode/pull/5154))

## What's new in 1.24.3
* Fix OmniSharp not found issue on Mono ([#5140](https://github.com/OmniSharp/omnisharp-vscode/issues/5140), PR: [#5141](https://github.com/OmniSharp/omnisharp-vscode/pull/5141))

## What's new in 1.24.2
* Support inlay hints ([#1932](https://github.com/OmniSharp/omnisharp-roslyn/issues/1932), PR: [#5107](https://github.com/OmniSharp/omnisharp-vscode/pull/5107))
* Pass "shell: true" as a spawn option when launching O# (PR: [#5125](https://github.com/OmniSharp/omnisharp-vscode/pull/5125))
* Add GoToTypeDefinition provider ([#4251](https://github.com/OmniSharp/omnisharp-vscode/issues/4251), PR: [#5094](https://github.com/OmniSharp/omnisharp-vscode/pull/5094))
* Quote launch paths when necessary ([#5099](https://github.com/OmniSharp/omnisharp-vscode/issues/5099), PR: [#5101](https://github.com/OmniSharp/omnisharp-vscode/pull/5101))
* Fix string escape for linux and unix (PR: [#5122](https://github.com/OmniSharp/omnisharp-vscode/pull/5122))
* Debounce diagnostic requests ([#5085](https://github.com/OmniSharp/omnisharp-vscode/issues/5085), PR: [#5089](https://github.com/OmniSharp/omnisharp-vscode/pull/5089))
* Add AnalyzeOpenDocumentsOnly (PR: [#5088](https://github.com/OmniSharp/omnisharp-vscode/pull/5088))
* Upgrade OmniSharp to 1.38.2:
    * Add analyze open documents only (PR: [omnisharp-roslyn#2346](https://github.com/OmniSharp/omnisharp-roslyn/pull/2346))
    * Create a new GoToTypeDefinition endpoint ([omnisharp-roslyn#2297](https://github.com/OmniSharp/omnisharp-roslyn/issues/2297), PR: [omnisharp-roslyn#2315](https://github.com/OmniSharp/omnisharp-roslyn/pull/2315))
    * Eliminate more instances of IWorkspaceOptionsProvider (PR: [omnisharp-roslyn#2343](https://github.com/OmniSharp/omnisharp-roslyn/pull/2343))
    * Update Build.md brew cask instructions (PR: [omnisharp-roslyn#2355](https://github.com/OmniSharp/omnisharp-roslyn/pull/2355))
    * Remove not used middleware extension methods and unify adding middleware (PR: [omnisharp-roslyn#2340](https://github.com/OmniSharp/omnisharp-roslyn/pull/2340))
    * Pass --overwrite when pushing build artifacts to azure (PR: [omnisharp-roslyn#2358](https://github.com/OmniSharp/omnisharp-roslyn/pull/2358))
    * Delete System.Configuration.ConfigurationManager from deployed packages ([#5113](https://github.com/OmniSharp/omnisharp-vscode/issues/5113), PR: [omnisharp-roslyn#2359](https://github.com/OmniSharp/omnisharp-roslyn/pull/2359))
    * Support inlay hints (PR: [omnisharp-roslyn#2357](https://github.com/OmniSharp/omnisharp-roslyn/pull/2357))
    * Update build tools to match .NET SDK 6.0.201 ([omnisharp-roslyn#2363](https://github.com/OmniSharp/omnisharp-roslyn/pull/2363))

## What's new in 1.24.1
* Only semantically highlight documents from uri.scheme 'file' (PR: [#5059](https://github.com/OmniSharp/omnisharp-vscode/pull/5059))
* Filter packages to install by framework before attempting install ([#5032](https://github.com/OmniSharp/omnisharp-vscode/issues/5032), PR: [#5041](https://github.com/OmniSharp/omnisharp-vscode/pull/5041))
* Update Razor's TextMate to latest. (PR: [#5012](https://github.com/OmniSharp/omnisharp-vscode/pull/5012))
* Upgrade OmniSharp to 1.38.1:
  * Reuse Roslyn's analyzer assembly loader (PR: [omnisharp-roslyn#2236](https://github.com/OmniSharp/omnisharp-roslyn/pull/2236))
  * Pass Completion, Rename and Block Structure options directly instead of updating the Workspace (PR: [omnisharp-roslyn#2306](https://github.com/OmniSharp/omnisharp-roslyn/pull/2306))
  * Update included build tool to match the current 6.0.200 sdk (PR: [omnisharp-roslyn#2329](https://github.com/OmniSharp/omnisharp-roslyn/pull/2329))
  * Fix concurrency issue in CSharpDiagnosticWorker (PR: [omnisharp-roslyn#2333](https://github.com/OmniSharp/omnisharp-roslyn/pull/2333))
  * run analyzers on multiple threads if allowed to (PR: [omnisharp-roslyn#2285](https://github.com/OmniSharp/omnisharp-roslyn/pull/2285))
  * Add MSBuild project to solution and apply the change to Roslyn workspace as a unit (PR: [omnisharp-roslyn#2314](https://github.com/OmniSharp/omnisharp-roslyn/pull/2314))
  * Updated to Roslyn 4.0.1 (PR: [omnisharp-roslyn#2323](https://github.com/OmniSharp/omnisharp-roslyn/pull/2323))
  * Enable OmniSharp.Cake tests for .NET 6 (PR: [omnisharp-roslyn#2307](https://github.com/OmniSharp/omnisharp-roslyn/pull/2307))
  * Handle completions with trailing whitespace on previous lines (PR: [omnisharp-roslyn#2319](https://github.com/OmniSharp/omnisharp-roslyn/pull/2319))
  * Update build bools to match .NET SDK 6.0.200 (PR: [omnisharp-roslyn#2347](https://github.com/OmniSharp/omnisharp-roslyn/pull/2347))

### Emmet support in Razor files

To enable emmet support, add the following to your settings.json:

```json
"emmet.includeLanguages": {
    "aspnetcorerazor": "html"
}
```

### Semantic Highlighting

The C# semantic highlighting support is in preview. To enable, set `editor.semanticHighlighting.enabled` and `csharp.semanticHighlighting.enabled` to `true` in your settings. Semantic highlighting is only provided for code files that are part of the active project.

To really see the difference, try the new Visual Studio 2019 Light and Dark themes with semantic colors that closely match Visual Studio 2019.

### Supported Operating Systems for Debugging

Currently, the C# debugger officially supports the following operating systems:

* X64 operating systems:
    * Windows 7 SP1 and newer
    * macOS 10.12 (Sierra) and newer
    * Linux: see [.NET Core documentation](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md#linux) for the list of supported distributions. Note that other Linux distributions will likely work as well as long as they include glibc and OpenSSL.
* ARM operating systems:
    * Linux is supported as a remote debugging target

### Found a Bug?

To file a new issue to include all the related config information directly from vscode by entering the command pallette with <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>
(<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS) and running `CSharp: Report an issue` command. This will open a browser window with all the necessary information related to the installed extensions, dotnet version, mono version, etc. Enter all the remaining information and hit submit. More information can be found on the [wiki](https://github.com/OmniSharp/omnisharp-vscode/wiki/Reporting-Issues).

Alternatively you could visit https://github.com/OmniSharp/omnisharp-vscode/issues and file a new one.

### Development

First install:

* Node.js (8.11.1 or later)
* Npm (5.6.0 or later)

To **run and develop** do the following:

* Run `npm i`
* Run `npm run compile`
* Open in Visual Studio Code (`code .`)
* _Optional:_ run `npm run watch`, make code changes
* Press <kbd>F5</kbd> to debug

To **test** do the following: `npm run test` or <kbd>F5</kbd> in VS Code with the "Launch Tests" debug configuration.

### License

Copyright © .NET Foundation, and contributors.

The Microsoft C# extension is subject to [these license terms](RuntimeLicenses/license.txt).
The source code to this extension is available on [https://github.com/OmniSharp/omnisharp-vscode](https://github.com/OmniSharp/omnisharp-vscode) and licensed under the [MIT license](LICENSE.txt).

## Code of Conduct

This project has adopted the code of conduct defined by the [Contributor Covenant](http://contributor-covenant.org/)
to clarify expected behavior in our community.
For more information see the [.NET Foundation Code of Conduct](http://www.dotnetfoundation.org/code-of-conduct).

## Contribution License Agreement

By signing the [CLA](https://cla.dotnetfoundation.org/OmniSharp/omnisharp-roslyn), the community is free to use your contribution to [.NET Foundation](http://www.dotnetfoundation.org) projects.

## .NET Foundation

This project is supported by the [.NET Foundation](http://www.dotnetfoundation.org).
