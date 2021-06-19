# UnrealEngine GenerateClangDatabase Improvements

A set of patches which expand the features of `UnrealBuildTool`'s `GenerateClangDatabase` mode.

The patches are based on this [pull-request](https://github.com/EpicGames/UnrealEngine/pull/6325) and have been rebased against UE version 4.26.2.

## Added arguments

| Argument                         | Description                                                                                                          |
| :------------------------------- | :------------------------------------------------------------------------------------------------------------------- |
| -ClangPath="clang++"             | Path to `clang++` (Default is `clang++`)                                                                             |
| -ForceGenerationOfEngineDatabase | If true compilation information for precompiled engine source files will be added                                    |
| -GenerateEntriesForHeaderFiles   | If true header files will be added to the compilation database in addition to source files.                          |
| -UseDefinitionHeader             | If true Definitions are written to a header file, this reduces the size of the compilation database.                 |
| -UseClangConfigFiles             | If true compilation flags are written to a .txt file, this drastically reduces the size of the compilation database. |

## Examples

_`Build.sh` can be found in `UnrealEngine/Engine/Build/BatchFiles/Linux`_

#### Generate compilation database for the engine

```
$ Build.sh UE4Editor Linux Development -Mode=GenerateClangDatabase
```

#### Generate compilation database for a project

```
$ Build.sh MyGameEditor Linux Development -Mode=GenerateClangDatabase -project="/path/to/MyGame.uproject"
```

## Installation

Apply each patch in order.
