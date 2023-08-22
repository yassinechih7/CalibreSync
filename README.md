# CalibreSync

CalibreSync is a script that helps you synchronize your Calibre library between your local machine and a remote storage location using the powerful tool `rclone`. This allows you to keep your eBook library consistent across different devices and platforms.

## Prerequisites

Before you can use CalibreSync, make sure you have the following installed:

- [rclone](https://rclone.org/): Rclone is a command-line program to manage files on cloud storage. It supports a wide variety of cloud storage providers, including Backblaze B2 which we'll be using in this project.

## Configuration

1. **Configure rclone**: Before you start using CalibreSync, you need to configure `rclone` to work with your Backblaze B2 account. You can find detailed instructions on how to set up rclone with Backblaze B2 [here](https://rclone.org/b2/).

2. **Set up environment variables**: Open your shell profile configuration file (e.g., `.zshrc`, `.bashrc`) and add the following lines to define your local Calibre directory and remote B2 bucket:

    ```bash
    local_calibre_dir="$HOME/my-b2-calibre-library"
    remote_b2_bucket="b2:my-b2-calibre-library"
    ```

    Make sure to adjust the paths to match your actual local directory and remote B2 bucket.

3. **Set up aliases**
   ```bash
     # Sync local to remote
    alias csync-remote="rclone sync $local_calibre_dir $remote_b2_bucket:"
    
    # Sync remote to local
    alias csync-local="rclone sync $remote_b2_bucket: $local_calibre_dir"
   ```
## Usage

CalibreSync provides two simple aliases that allow you to synchronize your Calibre library between your local machine and the remote B2 bucket.

### Sync Local to Remote

To synchronize your local Calibre library to the remote B2 bucket, use the following command:

```bash
csync-remote
```
