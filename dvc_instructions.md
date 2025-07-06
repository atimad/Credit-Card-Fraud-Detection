## 📦 Dataset Tracking with DVC

To track your dataset using [DVC](https://dvc.org/):

1. Install DVC:
   ```bash
   pip install dvc
   ```

2. Initialize DVC in your repo:
   ```bash
   dvc init
   ```

3. Add your dataset (e.g., `Data/creditcard.csv`):
   ```bash
   dvc add Data/creditcard.csv
   ```

4. Commit the generated `.dvc` file:
   ```bash
   git add Data/creditcard.csv.dvc .gitignore .dvc
   git commit -m "Track dataset using DVC"
   ```

5. (Optional) Configure a remote storage:
   ```bash
   dvc remote add -d myremote gdrive://your-folder-id
   dvc push
   ```

To retrieve the dataset later:
```bash
git clone https://github.com/your/repo.git
cd repo
dvc pull
```
