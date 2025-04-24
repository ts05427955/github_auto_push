# Auto Git Push Script README

## Purpose
This batch script (`@echo off.bat`) automates the process of committing and pushing changes to a GitHub repository. It is designed to streamline daily updates to the repository located at `C:\Users\Marco.ma\Documents\Embarcadero\Studio\Case1`.

## Functionality
The script performs the following tasks:
1. **Navigates to the repository directory**:
   - Changes the current directory to `C:\Users\Marco.ma\Documents\Embarcadero\Studio\Case1`.
2. **Logs the start time**:
   - Appends the current date and time to a log file (`git_auto_log.txt`) to record when the script starts.
3. **Stages all changes**:
   - Runs `git add .` to stage all modified and new files in the repository.
4. **Commits changes**:
   - Creates a commit with a message that includes the current date and time (e.g., "Daily auto commit 2025-04-24 14:30:00").
5. **Pushes to the remote repository**:
   - Pushes the committed changes to the `master` branch of the remote repository (`origin`).
6. **Logs the result**:
   - Checks the exit code of the push operation.
   - If successful (`errorlevel` is 0), logs "Push completed successfully" to `git_auto_log.txt`.
   - If failed, logs "Push failed with error code X" with the specific error code.
7. **Commented-out commands** (not currently executed):
   - Removing and re-adding the remote repository URL.
   - Displaying remote repository details (`git remote -v`).
   - Enabling Git credential storage (`git config --global credential.helper store`).

## Prerequisites
- **Git**: Must be installed and configured on the system with access to the target repository.
- **Repository**: The repository must already be initialized in `C:\Users\Marco.ma\Documents\Embarcadero\Studio\Case1` and linked to a remote GitHub repository (e.g., `https://github.com/Marco-ma-CSM/Marco-ma-CSM-CSM-Test.git`).
- **Permissions**: The user running the script must have write access to the repository and the local directory.

## Usage
1. Save the script as `@echo off.bat` (or another `.bat` file name).
2. Run the script manually by double-clicking it or via the command line:
   ```
   @echo off.bat
   ```
3. Alternatively, schedule it to run automatically using Windows Task Scheduler for daily execution.

## Log File
- The script creates/updates a file named `git_auto_log.txt` in the repository directory.
- This file records:
  - The start time of each execution.
  - Whether the push operation succeeded or failed, including any error codes.

## Notes
- **Commented-out commands**: The script includes commented lines (e.g., for setting the remote repository). Uncomment and configure these if the remote repository needs to be reconfigured.
- **Error Handling**: The script logs errors but does not retry failed operations. Modify the script if retry logic is needed.
- **Security**: Ensure the GitHub credentials are securely stored (e.g., using `git config --global credential.helper store`) to avoid authentication prompts.
- **Customization**: Adjust the repository path, branch name (`master`), or commit message format as needed.

## Example Log Output
```
Starting auto git push at 2025-04-24 14:30:00
Push completed successfully
```
or
```
Starting auto git push at 2025-04-24 14:30:00
Push failed with error code 1
```

## Troubleshooting
- **Push failures**: Check `git_auto_log.txt` for error codes. Common issues include:
  - No internet connection.
  - Incorrect remote URL or branch name.
  - Authentication issues (ensure credentials are configured).
- **Git not found**: Ensure Git is installed and added to the system PATH.
- **Permission errors**: Verify write access to the repository and local directory.

For further assistance, refer to the Git documentation or contact the repository administrator.