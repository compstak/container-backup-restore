# Usage

## Build

```sh
docker build -t backuper/backup:latest -f Dockerfile-backup .
docker build -t backuper/restore:latest -f Dockerfile-restore .
```

## Backup

```sh
docker run -it --rm --mount type=bind,source=<output directory>,target=/out --mount source=<volume to be backed up>,target=/in,readonly -e OUTPUT_FILE=<name of the file>  backuper/backup:latest
```

This will save the full content of `<volume to be backed up>` in the `<output directory>` under the name `<name of the file>.tar.gz`

## Restore

```sh
docker run -it --rm --mount type=bind,source=<input directory>,target=/in --mount source=<volume to be restored>,target=/out -e OUTPUT_FILE=<name of the file>  backuper/restore:latest
```

This will restore the full content of save the full content of `<name of the file>.tar.gz` in the `<input directory>` to `<volume to be restored>`
