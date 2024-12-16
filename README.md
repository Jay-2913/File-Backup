# File-Backup
Here's a description for your README file that explains the purpose and functionality of a Python script for backing up files:

---

## File Backup Script

This Python script provides a simple and efficient way to back up files from one directory to another. It can be used to create copies of important files and store them in a backup directory, ensuring data safety and redundancy.

### Prerequisites

Before running the script, make sure you have Python installed on your system. No additional libraries are required for this script as it uses built-in modules.

### Usage

The script takes two arguments: the source directory containing the files to be backed up and the destination directory where the backup files will be stored.

### Features

- **Copy Files**: The script copies all files from the source directory to the destination directory.
- **Create Backup Directory**: If the destination directory does not exist, the script will create it.
- **Overwrite Existing Files**: If files with the same names already exist in the destination directory, they will be overwritten.

### Example

Below is an example of how to use the script:

1. **Source Directory**: The directory containing the files to be backed up.
2. **Destination Directory**: The directory where the backup files will be stored.

```python
import os
import shutil

def backup_files(source_dir, backup_dir):
    if not os.path.exists(backup_dir):
        os.makedirs(backup_dir)
        
    for filename in os.listdir(source_dir):
        source_file = os.path.join(source_dir, filename)
        backup_file = os.path.join(backup_dir, filename)
        if os.path.isfile(source_file):
            shutil.copy2(source_file, backup_file)
            print(f"Backed up {filename} to {backup_dir}")

# Example usage
source_directory = '/path/to/source_directory'
backup_directory = '/path/to/backup_directory'

backup_files(source_directory, backup_directory)
```

### How It Works

1. **Import Modules**:
   - `os`: For interacting with the operating system.
   - `shutil`: For high-level file operations like copying.
   
2. **Create Backup Directory**:
   - The script checks if the backup directory exists and creates it if it does not.

3. **Copy Files**:
   - The script iterates through the files in the source directory and copies each file to the backup directory using `shutil.copy2()`, which preserves metadata like timestamps.

4. **Print Confirmation**:
   - After copying each file, the script prints a confirmation message.

### Conclusion

This file backup script is a simple yet powerful tool for ensuring your important files are safely backed up. By automating the backup process, it helps prevent data loss and ensures you have copies of your files stored in a secure location.

---

Feel free to customize this description further based on your project's specifics! 😊📚🚀
