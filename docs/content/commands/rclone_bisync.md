---
title: "rclone bisync"
description: "Perform bidirectional synchronization between two paths."
slug: rclone_bisync
url: /commands/rclone_bisync/
versionIntroduced: v1.58
# autogenerated - DO NOT EDIT, instead edit the source code in cmd/bisync/ and as part of making a release run "make commanddocs"
---
# rclone bisync

Perform bidirectional synchronization between two paths.

## Synopsis

Perform bidirectional synchronization between two paths.

[Bisync](https://rclone.org/bisync/) provides a
bidirectional cloud sync solution in rclone.
It retains the Path1 and Path2 filesystem listings from the prior run.
On each successive run it will:
- list files on Path1 and Path2, and check for changes on each side.
  Changes include `New`, `Newer`, `Older`, and `Deleted` files.
- Propagate changes on Path1 to Path2, and vice-versa.

See [full bisync description](https://rclone.org/bisync/) for details.


```
rclone bisync remote1:path1 remote2:path2 [flags]
```

## Options

```
      --check-access            Ensure expected RCLONE_TEST files are found on both Path1 and Path2 filesystems, else abort.
      --check-filename string   Filename for --check-access (default: RCLONE_TEST)
      --check-sync string       Controls comparison of final listings: true|false|only (default: true) (default "true")
      --filters-file string     Read filtering patterns from a file
      --force                   Bypass --max-delete safety check and run the sync. Consider using with --verbose
  -h, --help                    help for bisync
      --localtime               Use local time in listings (default: UTC)
      --no-cleanup              Retain working files (useful for troubleshooting and testing).
      --remove-empty-dirs       Remove empty directories at the final cleanup step.
  -1, --resync                  Performs the resync run. Path1 files may overwrite Path2 versions. Consider using --verbose or --dry-run first.
      --workdir string          Use custom working dir - useful for testing. (default: $HOME/.cache/rclone/bisync)
```

See the [global flags page](/flags/) for global options not listed here.

## SEE ALSO

* [rclone](/commands/rclone/)	 - Show help for rclone commands, flags and backends.

