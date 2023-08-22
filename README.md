# CalibreSync
Sync calibre library using rclone



```
local_calibre_dir="$HOME/my-b2-calibre-library"
remote_b2_bucket="b2:my-b2-calibre-library"

# Sync local to remote
alias csync-remote="rclone sync $local_calibre_dir $remote_b2_bucket:"

# Sync remote to local
alias csync-local="rclone sync $remote_b2_bucket: $local_calibre_dir"
```
