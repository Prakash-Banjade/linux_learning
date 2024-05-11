## Back up files by compressing them

Here we have used `tar` command to compress files.
To compress file using tar command, we use `tar czf` command.

```bash
#!/bin/bash

src_dir=/home/ubuntu/scripts # source dir that needs backup
tgt_dir=/home/ubuntu/backups # target dir where backup will be saved

curr_timestamp=$(date "+%Y-%m-%d-%H-%M-%S") # current timestamp
backup_file=$tgt_dir/$curr_timestamp.tgz # backup file name

echo "Taking backup on $curr_timestamp" 

tar czf $backup_file --absolute-names $src_dir # `--absolute-names` will include the absolute path in the backup file, this command compresses the files in the `scripts` directory

echo "Backup done"
```

This script will create a backup of the `scripts` directory and save it in the `backups` directory. 

**Note**: /backups must be created before running this script

## Restore files by decompressing them

```bash
#!/bin/bash

src_dir=/home/ubuntu/backups # source dir that needs backup
tgt_dir=/home/ubuntu/scripts # target dir where backup will be restored

curr_timestamp=$(date "+%Y-%m-%d-%H-%M-%S") # current timestamp
backup_file=$src_dir/$curr_timestamp.tgz # backup file name

echo "Restoring backup on $curr_timestamp"

tar xf $backup_file -C $tgt_dir # `--absolute-names` will include the absolute path in the backup file, this command decompresses the files in the `scripts` directory

echo "Restore done"
```

You can run the script above or simply run a command on the terminal as:

```bash
tar xf $backup_file -C $tgt_dir
```