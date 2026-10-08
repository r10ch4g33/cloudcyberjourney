# Project: Managing File Permissions in Linux

## Project Description
The research team at my organization needed to update file permissions within the projects directory to ensure proper authorization levels and maintain system security. 

---

## 1. Check File and Directory Details
I used the following command to check existing permissions, including hidden files:

using 'bash':
cd ./projects
ls -la

2. Deconstructing the Permissions String
The 10-character string can be broken down into sections:

1st character: File type (d for directory, - for regular file).

2nd-4th characters: User permissions (r, w, x).

5th-7th characters: Group permissions (r, w, x).

8th-10th characters: Other users' permissions (r, w, x).
# Remove write access for 'other' on project_k.txt
chmod o-w project_k.txt

3. Changing File and Directory Permissions
To meet organizational requirements, I modified access using the chmod command:
# Secure a hidden project file
chmod u-w,g-w,g+r .project_x.txt

# Restrict directory access
chmod g-x drafts

Summary
I successfully updated file and directory permissions to align with security policies, utilizing ls for auditing and chmod for precise access control modifications.
