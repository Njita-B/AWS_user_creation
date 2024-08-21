AWS_user_creation Automated process

## **Part 1**

- Automation Script for creating users by ‘AWS CLI’ from CloudShell;
- Converting the 'user migration spreadsheet' according to the script (”column names” and “.csv format”)
- Run Automation Script;
- Validate users created.

### Checking the Users Grupos created:

- **CloudAdmin**
- **DBA**
- **LinuxAdmin**
- **NetworkAdmin**
- **Trainees**


## Let’s Download and Analyze the Automation Script:

```bash
wget https://tcb-bootcamps.s3.amazonaws.com/bootcamp-aws/en/aws-iam-create-user.sh
```

***VSCode - used to analyze the script file:***

[Download Visual Studio Code - Mac, Linux, Windows](https://code.visualstudio.com/download)

### IT_Team_ABC-Company.xlsx

- Remove Name column
- Rename Email column to '**user**'
- Remove "@company.com" from Email column
- Rename Team column to '**group**'
- Rename '**group**' column based  on AWS groups created
- Add '**password**' column: **ChangeMe123456!**

✔ Save As... **CSV Format** [ **CSV (Comma Demilited) (*.csv)** ]

***users.csv***

✔ Let’s test using only 4 records!

✔ Salce As... **CSV Format** [ **CSV (Comma Demilited) (*.csv)** ]

***users2.csv***

### AWS Cloud Shell  [ It already comes with AWS CLI installed! ]

1. Access **AWS Cloud Shell**

2. Install '**dos2unix**' 

```bash
sudo yum install dos2unix -y
```

3. Create a file aws-iam-create-user.sh
   Add script from repo Njita-B/AWS_user_creation master branch

5. Change script’s permissions

```bash
ls -la
chmod +x aws-iam-create-user.sh
ls -la
```

5. Upload 'users2.csv' file

```bash
# validating file content

cat users2.csv
```

6. Run the script

```bash
./aws-iam-create-user.sh users2.csv
```

## Validating users created

IAM | Users | Groups | Permissions

## Attach Policy to allow users to change their passwords:

Acesse  **User groups** | **Permission** | **Add Permission**/**Attach Police** 

**IAMUserChangePassword**


