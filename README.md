# wsp
Workspace Command Line Tool

## Plan

```wsp``` will be a tool to dynamically populate a directory with the files that one needs in a chosen context.

It will be comprised of the following parts:

* A scanner that detects newer files and files whose mtime is newer than last scan.
* Several metadata (faucets) extractors that fetch and store faucets from files.
* The ```wsp``` tool that moves files that match certain criteria, defined as "a workspace."
* All files in the workspace are pushed into a store, where they are saved in a flat directory structure with a unique filename.
  The filename does not change on newer versions, or different content, of the file, which makes using another VCS easier. The actual file name (maybe also a relative subdirectory) are just metadata properties.
  To be defined how to best handle file renames.
* A workspace is defined by a configuration file, also writable by the ```wsp``` tool.
* All files are pushed back into the store when done, with another ```wsp``` subcommand.
* [lowprio] Hooks to invoke VCS commands (for example.)
* [lowprio] Apply some rules to create the workspace directory structure.
* [lowprio] Different filenames and relative directory structure for each workspace are remembered.

To be defined: what backing storage to use for the metadata repository. Is a hierharchical key-value enough? Is SQL needed?
