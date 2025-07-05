## Supplementary comments： Data versioning implementation

### 1. LakeFS
I used LakeFS to version the dataset using Git-like operations on data:

#### Setup:
Installed LakeFS via terminal and configured using lakefsctl.

Created a repository mlopsa1 and initialized the default branch main.

#### Versioning Workflow:

v1: Uploaded the original athletes.csv to the main branch using LakeFS UI.

v2:

Created a new branch v2 from main.

Cleaned the data (removing outliers, irrelevant columns, and survey responses).

Committed the cleaned dataset to the v2 branch.

#### Switching: 

Switched between versions by checking out different branches in LakeFS (e.g., main to v2), enabling reproducible experiments without overwriting data.

### 2. Git LFS
I used Git Large File Storage (LFS) to track the dataset files directly in Git:

#### Setup:

Installed Git LFS via pip install git-lfs.

Tracked athletes.csv using git lfs track.

#### Versioning Workflow:

v1: Committed the raw dataset as a versioned file in Git.

v2:

Cleaned the data as per the assignment instructions.

Overwrote the original file or created a new file for v2.

Committed the cleaned dataset as a new Git commit.

#### Switching: 
Switched versions manually using git checkout <commit-hash> or by reverting commits. No native branching for data, so version control is less structured and harder to manage than LakeFS.
