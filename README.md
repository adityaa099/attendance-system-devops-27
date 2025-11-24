Attendance System – DevOps 27

This project is a Linux Automation + Git Version Control assignment demonstrating directory management, data extraction, backup handling, branching workflow, and pull request (PR) management.

📂 Project Structure
attendance/
│
├── raw/
│   └── data.csv               # Original attendance data (13 rows)
│
├── processed/
│   └── present.txt            # Extracted list of present students
│
├── backup/
│   └── present-YYYY-MM-DD.txt # Daily backup with date suffix
│
└── README.md

🛠️ Part A – Linux Automation
✔️ 1. Created attendance directory structure
/home/aditya/attendance/{raw,processed,backup}

✔️ 2. Created CSV file (raw/data.csv) containing:

RollNo

Name

Status (Present/Absent)

✔️ 3. Extracted “Present” entries into processed/present.txt
grep "Present" raw/data.csv > processed/present.txt

✔️ 4. Created backup with date suffix
cp processed/present.txt backup/present-$(date +%Y-%m-%d).txt

✔️ 5. Displayed only student names
cut -d',' -f2 raw/data.csv

🔀 Part B – GitHub Version Control
✔️ 1. Initialized Git repository
git init

✔️ 2. Added all files and made initial commit
git add .
git commit -m "Initial attendance data upload"

✔️ 3. Created data-cleaning branch and cleaned present.txt
git checkout -b data-cleaning
sed -i '/^$/d' processed/present.txt
git add processed/present.txt
git commit -m "Cleaned present.txt by removing blank lines"

✔️ 4. Pushed both branches to GitHub
git push -u origin main
git push -u origin data-cleaning

✔️ 5. Created Pull Request (PR) on GitHub

Merged data-cleaning → main successfully.

🚀 Tools Used

Ubuntu Linux

Bash Shell

Git & GitHub

grep, sed, cut, tail commands

✨ Author

Aditya Chouksey 
DevOps Student 
