# pa-permission-diff-analyzer
Compares permissions between two directories or snapshots, highlighting discrepancies and potential misconfigurations. The comparison covers files and directories themselves, including the two directory roots and every subdirectory in the compared set. Only the Python standard library is required; the `rich` library is optional and only formats the console table. - Focused on Tools for analyzing and assessing file system permissions

## Install
`git clone https://github.com/ShadowStrikeHQ/pa-permission-diff-analyzer`

## Usage
`python3 main.py [DIR1] [DIR2] [params]`

## Parameters
- `-h`: Show help message and exit
- `--recursive`: Recursively compare subdirectories. Without this flag only the top level entries of the two directories are compared; with it the whole tree under both directories is compared.
- `--ignore-ownership`: Ignore differences in file ownership (user/group).
- `--report-file`: Path to save the report to a file. The saved report holds the full text report in both text and rich output formats.
- `--output-format`: Format of the output: text or rich (requires rich library). Defaults to text.
- `--log-level`: Set the logging level. Defaults to INFO.

## Behavior notes
- Both arguments must be directories. Passing a regular file as either argument is an input error and the run exits 1 without printing a report.
- An entry present on one side only is reported with an empty permission set for the missing side.
- Directory entries are reported by their relative path, and the two roots are reported as `.` when their own permissions differ.

## License
Copyright (c) ShadowStrikeHQ
