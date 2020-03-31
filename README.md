# Usage

## Build

```sh
docker build -t backuper/backup:latest backup/
```

## Backup
```sh
docker run -it --rm --mount type=bind,source=<output directory>,target=/out --mount source=<volume to be backed up>,target=/in,readonly -e OUTPUT_FILE=<name of the file>  backuper/backup:latest
```

This will save the full content of `<volume to be backed up>` in the `<output directory>` under the name `<name of the file>.tar.gz`