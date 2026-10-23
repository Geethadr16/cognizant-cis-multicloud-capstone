
# Linux Administration | Technical Capstone Lab

## 1. Overview

This lab documents Linux administration exercises completed
during the Cognizant CIS Multicloud technical training program.

The activities focused on command-line operations, filesystem
management, permissions, ownership, file searching, and software
package management.

The training combined practical Linux exercises with theoretical
coverage of administration concepts across Linux distributions.

## 2. Lab Environment

| Component | Technology / Tool |
|---|---|
| Operating System | Linux Virtual Machine |
| Interface | Terminal / Command-Line Interface |
| Shell | Linux shell |
| Package Manager | APT |
| Software Package | Nginx |
| Administration Tools | `mkdir`, `chmod`, `chown`, `grep`, `find`, `cp`, `mv`, `rm` |

## 3. Technical Objectives

- Perform essential Linux command-line operations.
- Create and manage files and directories.
- Understand file permissions and ownership.
- Search for files and text patterns.
- Work with absolute and relative paths.
- Install and remove software packages.
- Understand package repositories and dependencies.
- Explore package management across Linux distributions.

---

## 4. Assignment 1 — Linux Commands & Administration

### 4.1 Directory Creation

The `mkdir` command creates directories within the Linux filesystem.

```bash
mkdir linux_project
```

The directory is created relative to the current working directory.

### 4.2 File Permission Management

The `chmod` command modifies access permissions.

```bash
chmod 755 linux_project
```

**Understanding Permission 755**

| Category | Permission | Access |
|---|---|---|
| Owner | `rwx` (7) | Read, write, execute |
| Group | `r-x` (5) | Read, execute |
| Others | `r-x` (5) | Read, execute |

For directories, read permission allows listing directory entries,
while execute permission allows directory traversal.

### 4.3 Ownership Management

The `chown` command changes file or directory ownership.

```bash
sudo chown user:user linux_project
```

Here, `user:user` represents an example user and group.
The specified user and group must exist on the system.

### 4.4 Searching Text with grep

The `grep` command searches file contents for matching patterns.

```bash
grep "error" logfile.txt
```

This displays lines containing `error` from `logfile.txt`.

### 4.5 Finding Files with find

The `find` command searches filesystem locations using
specified conditions.

```bash
find /home -name "*.txt"
```

This recursively searches `/home` for entries whose names
end in `.txt`.

To restrict the search to regular files:

```bash
find /home -type f -name "*.txt"
```

The second command is an additional example demonstrating
how the `-type f` option filters regular files.

### Technical Outcome

Practiced foundational Linux commands for directory management,
permissions, ownership, and searching.

---

## 5. Assignment 2 — Directory & File Management

### Objective

Create a structured filesystem and perform file-management
operations using Linux commands.

### 5.1 Create Nested Directories

```bash
mkdir -p /home/student/linux_practice/docs/backup
```

The `-p` option creates missing parent directories.

**Directory Structure**

```text
/home/student/linux_practice/
└── docs/
    └── backup/
```

### 5.2 Create Multiple Text Files

Navigate to the project directory:

```bash
cd /home/student/linux_practice
```

Create ten text files:

```bash
touch file{1..10}.txt
```

This command uses Bash brace expansion to create ten files
in the current working directory.

### 5.3 Copy Files

The original assignment covered copying files using `cp`.

For the directory structure created above, the following
command copies text files into the backup directory:

```bash
cp *.txt docs/backup/
```

**Technical Explanation:**

- `cp` copies files.
- `*.txt` selects matching text files in the current directory.
- `docs/backup/` specifies the destination directory.

The assignment also references the relative-path command:

```bash
cp *.txt backup/
```

This form works when an existing `backup` directory is
available relative to the current working directory.

### 5.4 Move Files

```bash
mv file1.txt docs/
```

This moves `file1.txt` from the project directory
into the existing `docs` directory.

The `mv` command can also rename files and directories.

### 5.5 Remove Files and Directories

Remove a file:

```bash
rm file2.txt
```

The `rm` command removes the specified file.

**Additional reference command:**

```bash
rmdir empty_directory
```

The `rmdir` command removes an empty directory.
This is included as a related Linux filesystem concept.

### 5.6 Absolute and Relative Paths

**Absolute Path**

```text
/home/student/linux_practice/docs
```

An absolute path begins at the filesystem root `/`.

**Relative Path**

```text
docs/backup
```

A relative path is interpreted from the current
working directory.

### 5.7 Verification Commands

The following commands can be used to inspect
filesystem operations:

```bash
pwd
ls -l
find . -type f
```

| Command | Purpose |
|---|---|
| `pwd` | Display the current working directory |
| `ls -l` | List files with permissions and ownership information |
| `find . -type f` | Find regular files below the current directory |

These are useful verification commands for Linux
filesystem administration.

### Technical Outcome

Practiced creating nested directories, managing multiple
files, copying and moving files, removing files,
and navigating the Linux filesystem.

---

## 6. Assignment 3 — Linux Package Management

### Objective

Understand repository-based software installation,
package removal, and dependency management.

### 6.1 Update Package Information

```bash
sudo apt update
```

Refreshes package information from configured repositories.

This command updates the package index; it does not upgrade
all installed software.

### 6.2 Install Nginx

```bash
sudo apt install nginx
```

Installs the Nginx package and resolves required dependencies
through APT.

### 6.3 Remove Nginx

```bash
sudo apt remove nginx
```

Removes the Nginx package while potentially retaining
package-managed configuration files.

### 6.4 APT Package Management Concepts

| Command | Purpose |
|---|---|
| `apt update` | Refresh package information |
| `apt install` | Install software packages |
| `apt remove` | Remove installed packages |
| `apt purge` | Remove packages and package-managed configuration files |
| `apt autoremove` | Remove automatically installed dependencies no longer required |

### 6.5 Additional Linux Package Management Concepts

Alongside practical APT exercises, the training covered
RPM-based package management during theory sessions.

| Tool | Purpose | Learning Type |
|---|---|---|
| APT | Package management on Debian/Ubuntu-based systems | Practical Lab |
| YUM | Repository-based package management on RPM-based Linux distributions | Theory |
| RPM | Installing, querying, and managing RPM packages | Theory |

This provided an understanding of software management
across different Linux distributions.

### Technical Outcome

Practiced APT-based software management and developed
conceptual knowledge of RPM-based package-management tools.

---

## 7. Verification & Technical Results

The completed assignments include terminal screenshots
documenting Linux command-line exercises.

| Assignment | Technical Activity | Supporting Evidence |
|---|---|---|
| Linux Commands | Directory operations, permissions, ownership, searching | Linux commands screenshot |
| File Management | Nested directories, file creation, copying, moving | Directory management screenshot |
| Package Management | APT operations and Nginx package management | Package management screenshot |

The commands and explanations document the assignment
activities and associated Linux administration concepts.

---

## 8. Supporting Evidence

### 8.1 Linux Commands

Terminal-based command execution covering foundational
Linux administration operations.

![Linux Commands](Screenshots/Linux-Commands.png)

### 8.2 Directory and File Management

Directory creation, filesystem organization,
and file-management operations.

![Directory and File Management](Screenshots/Directory-Management.png)

### 8.3 Package Management

APT package-management operations and associated
terminal output.

![Package Management](Screenshots/Package-Management.png)

---

## 9. Key Learning Outcomes

- Practiced Linux command-line administration.
- Understood filesystem hierarchy and directory organization.
- Explored numeric permissions and ownership management.
- Used `grep` and `find` for searching and filtering.
- Practiced file creation, copying, moving, and removal.
- Understood absolute and relative filesystem paths.
- Practiced software package management using APT.
- Learned the differences between APT, YUM, and RPM.
- Strengthened Linux fundamentals relevant to cloud
  infrastructure and DevOps engineering.

---

## 10. Lab Summary

This Linux administration capstone covered command-line
operations, filesystem management, permissions, ownership,
searching, and software package management.

The practical assignments and supporting screenshots
demonstrate foundational Linux administration skills
developed during Cognizant CIS Multicloud technical training.

The exercises strengthened skills relevant to Linux
system administration, cloud infrastructure,
and DevOps engineering.
