# Project Overview

This project demonstrates the use of **DVC (Data Version Control)** for managing data and experiments. The repository includes a Python environment setup script and a `data` folder containing versioned data files.

## Folder Structure

```
/home/anouar/Desktop/dvcdemo/
├── data/
│   └── data.txt
├── setup_env.sh
├── Readme.md
```

## Setup Instructions

1. Clone the repository:
    ```bash
    git clone <repository-url>
    cd dvcdemo
    ```

2. Set up the Python environment:
    ```bash
    bash setup_env.sh
    ```

3. Install DVC if not already installed:
    ```bash
    pip install dvc
    ```

## DVC Workflow

### Adding Data to DVC
The `data/data.txt` file is tracked using DVC. To add new data:
```bash
dvc add data/data.txt
```
This creates a `.dvc` file to track the data.

### Committing Changes
After adding or modifying data, commit the changes:
```bash
git add data/data.txt.dvc .gitignore
git commit -m "Add or update data.txt"
```

### Updating Data
To update the data file:
1. Replace or modify `data/data.txt`.
2. Run:
    ```bash
    dvc add data/data.txt
    git add data/data.txt.dvc
    git commit -m "Update data.txt"
    ```

### Reverting to Previous Data
To revert to a previous version of the data:
```bash
git checkout <commit-hash>
dvc checkout
```

### Pulling Data from Remote
If the data is stored remotely, pull it using:
```bash
dvc pull
```

## Notes
- Ensure that the `data/` folder is listed in `.gitignore` to avoid committing large files directly to Git.
- Use `dvc push` to upload data to a remote storage.

## References
- [DVC Documentation](https://dvc.org/doc)
- [Git Documentation](https://git-scm.com/doc)