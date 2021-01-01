# superfind

Find files and folders on the filesystem including archives.

## SYNOPSIS

```
superfind STARTING-PATH PATTERN
```

## DESCRIPTION

Example usage:

```bash
superfind /backup/path '.*checkboxes.js$'
```

searches the filesystem recursively starting at `/backup/path` for files matching the regular expression pattern `.*checkboxes.js$`. If an archive is encountered (e.g. a .zip file or a tarball), the same pattern will be tested against paths found within the archive. Example output:

```
FIND	/backup/path/live/website/js/checkboxes.js
/backup/path/snapshot-2020-12-31.tar.gz	website/js/checkboxes.js
```

All searches are case-insensitive. Only files are matched.

## PREREQUISITES

* Python 3
* GNU find

## TO DO

- [ ] Are there other/better free software utilities that do serve the same purpose as this program? list/promote them.
- [ ] Right now we check if something is an archive by matching the file extension. Consider checking file magic number instead, like the `file` command?
- [ ] Recurse if an archive is found in an archive.
- [ ] Go parallel: search through archives using another core (separate thread/process).

## COPYLEFT AND LICENSE

* Copyright ©2020 Adam Monsen &lt;haircut@gmail.com&gt;
* License: AGPL v3 or later (see COPYING)
