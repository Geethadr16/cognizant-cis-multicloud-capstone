
# ⚡ PowerShell Administration | Scripting & Infrastructure Automation Lab

## 📌 1. Overview

This module documents PowerShell administration exercises completed during the **Cognizant CIS Multicloud technical capstone training program**.

The assignments focused on Windows process and service monitoring, PowerShell cmdlets, pipeline operations, command aliases, CSV export, JSON conversion, and text file manipulation.

The exercises introduced PowerShell as a command-line shell and scripting environment for Windows administration, structured data processing, and foundational infrastructure automation.

**Assignments Covered:**

1. **Cmdlets & Pipelines:** Process monitoring, service monitoring, pipeline filtering, and alias management.
2. **File Conversion:** Exporting process data to CSV, converting CSV data to JSON, and working with text files.

## 🖥️ 2. Lab Environment & Technologies

| Component | Technology / Tool |
|---|---|
| Operating Environment | Windows |
| Command-Line Shell | Windows PowerShell |
| Administration Interface | PowerShell Console |
| Process Monitoring | `Get-Process` |
| Service Monitoring | `Get-Service` |
| Pipeline Filtering | `Where-Object` |
| Alias Management | `Get-Alias`, `Set-Alias`, `New-Alias` |
| Data Export | `Export-Csv` |
| Data Conversion | `Import-Csv`, `ConvertTo-Json` |
| File Operations | `Get-Content`, `Set-Content` |
| Data Formats | CSV, JSON, TXT |

The original assignment specifically documents `Get-Process`, `Get-Service`, `Where-Object`, `Export-Csv`, `Get-Content`, and `Set-Content`.

Additional cmdlets shown in this README are included as reference examples where appropriate.

## 🎯 3. Technical Objectives

- Understand PowerShell command structure and syntax.
- Execute built-in cmdlets for Windows administration.
- Retrieve running process information.
- Inspect Windows service status.
- Understand pipeline-based object processing.
- Filter process information using `Where-Object`.
- Explore built-in and custom command aliases.
- Export structured process information to CSV.
- Understand CSV-to-JSON conversion.
- Read and modify text file contents.
- Develop foundational scripting and automation skills.

---

## 💻 4. Assignment 1 — PowerShell Cmdlets & Pipelines

### 4.1 Understanding PowerShell Cmdlets

**Objective:** Execute fundamental PowerShell commands for system administration.

PowerShell cmdlets are commands designed to perform specific operations.

They commonly follow the **Verb-Noun** naming convention.

**Examples:**

| Cmdlet | Purpose |
|---|---|
| `Get-Process` | Retrieves running processes |
| `Get-Service` | Retrieves Windows service information |
| `Where-Object` | Filters objects based on specified conditions |
| `Get-Alias` | Displays command aliases |

Unlike traditional text-based command pipelines, PowerShell pipelines can pass structured objects between commands.

### 4.2 Process Monitoring with Get-Process

The assignment covered retrieving information about running processes.

**Command Used:**

```powershell
Get-Process
```

**Technical Explanation:**

`Get-Process` retrieves information about active processes on the local computer.

Depending on the available properties and display format, process information can include:

- Process name
- Process ID (PID)
- CPU time
- Memory usage
- Process status information

**Administrative Use Cases:**

- Identifying running applications.
- Inspecting process resource consumption.
- Investigating system performance issues.
- Supporting basic Windows troubleshooting.

### 4.3 Service Monitoring with Get-Service

The assignment also covered Windows service monitoring.

**Command Used:**

```powershell
Get-Service
```

**Technical Explanation:**

`Get-Service` retrieves information about services registered with Windows.

Common information includes:

| Property | Description |
|---|---|
| Status | Indicates whether a service is running or stopped |
| Name | Internal service name |
| DisplayName | Human-readable service name |

**Administrative Use Cases:**

- Checking service availability.
- Identifying stopped services.
- Reviewing services during troubleshooting.
- Supporting routine Windows administration.

### 4.4 Understanding PowerShell Pipelines

**Objective:** Use pipelines to process and filter command output.

The pipeline operator (`|`) passes the output of one command to another.

**Basic Structure:**

```text
Command 1 | Command 2
```

**Conceptual Workflow:**

```text
       Get-Process
            |
            | Process Objects
            v
       Where-Object
            |
            | Apply Filter
            v
       Filtered Results
```

PowerShell pipelines support object-based operations such as:

- Filtering
- Sorting
- Selecting properties
- Exporting data
- Processing command results

### 4.5 Filtering Processes Using Where-Object

The original assignment includes the following command:

```powershell
Get-Process | Where-Object {$_.CPU -gt 10}
```

**Command Breakdown:**

| Component | Function |
|---|---|
| `Get-Process` | Retrieves running processes |
| `|` | Passes process objects to the next command |
| `Where-Object` | Filters the received objects |
| `$_` | Represents the current pipeline object |
| `.CPU` | Accesses the process CPU property |
| `-gt 10` | Selects values greater than 10 |

**Important Technical Detail:**

The `CPU` property returned by `Get-Process` represents accumulated processor time in seconds, not the instantaneous CPU utilization percentage.

Therefore, this command selects processes that have accumulated more than **10 seconds of CPU time**.

It does not directly identify processes currently using more than 10% CPU.

### 4.6 Understanding PowerShell Aliases

**Objective:** Explore command aliases and create shortcuts for frequently used commands.

An alias is an alternative name for a PowerShell command.

Aliases simplify command entry and can improve efficiency during interactive administration.

**Built-in Alias Example:**

```powershell
gps
```

`gps` is a built-in alias for `Get-Process`.

### 4.7 Exploring Existing Aliases

**Reference Command:**

```powershell
Get-Alias
```

This displays aliases available in the current PowerShell session.

To inspect a specific alias:

```powershell
Get-Alias gps
```

### 4.8 Creating Custom Aliases

The original assignment covered creating user-defined aliases.

**Illustrative Example:**

```powershell
Set-Alias -Name procs -Value Get-Process
```

The alias can then be used as:

```powershell
procs
```

This executes the associated `Get-Process` command.

Custom aliases created interactively generally apply to the current session unless saved through an appropriate persistence mechanism, such as a PowerShell profile.

### Technical Outcome

Practiced Windows process and service inspection, PowerShell pipeline filtering, and command alias concepts.

These activities strengthened foundational command-line administration and troubleshooting skills.

---

## 📂 5. Assignment 2 — File Conversion & Data Processing

### 5.1 Objective

Understand how PowerShell can collect system information, export structured data, convert file formats, and manipulate text files.

The assignment covered:

- Process data collection.
- CSV file generation.
- CSV-to-JSON conversion.
- Reading text files.
- Writing and modifying text file content.

### 5.2 Export Process Information to CSV

The original assignment documents the following command:

```powershell
Get-Process | Export-Csv processes.csv
```

**Technical Explanation:**

1. `Get-Process` retrieves process information.
2. The pipeline passes process objects to `Export-Csv`.
3. `Export-Csv` serializes object properties into CSV format.
4. The output is saved to `processes.csv`.

**Result:**

A CSV file containing process-related information is generated.

**Administrative Applications:**

- Collecting process inventory data.
- Creating system administration reports.
- Preserving process information for later analysis.
- Supporting repeatable data collection.

### 5.3 Understanding CSV Files

CSV stands for **Comma-Separated Values**.

It is a structured text format commonly used for exchanging tabular data.

**Illustrative CSV Structure:**

```csv
ProcessName,Id
explorer,1234
notepad,5678
```

The example above demonstrates CSV structure and does not represent actual process IDs from the training environment.

### 5.4 Converting CSV Data to JSON

The original assignment covered converting CSV data into JSON format.

JSON is commonly used for structured data exchange between applications, APIs, and automation tools.

**Illustrative PowerShell Workflow:**

```powershell
Import-Csv processes.csv | ConvertTo-Json | Set-Content processes.json
```

**Command Breakdown:**

| Cmdlet | Purpose |
|---|---|
| `Import-Csv` | Reads CSV records into PowerShell objects |
| `ConvertTo-Json` | Converts objects into JSON-formatted text |
| `Set-Content` | Writes the JSON text to a file |

**Data Conversion Workflow:**

```text
          CSV File
              |
              v
          Import-Csv
              |
              v
       PowerShell Objects
              |
              v
         ConvertTo-Json
              |
              v
          Set-Content
              |
              v
          JSON File
```

This command is a reference implementation of the conversion task described in the assignment.

### 5.5 Understanding JSON

JSON stands for **JavaScript Object Notation**.

It represents structured information using objects, arrays, and values.

**Illustrative JSON Structure:**

```json
[
  {
    "ProcessName": "explorer",
    "Id": "1234"
  },
  {
    "ProcessName": "notepad",
    "Id": "5678"
  }
]
```

JSON is commonly used in:

- REST APIs
- Configuration files
- Automation workflows
- Application integrations
- Cloud service interfaces

### 5.6 Reading Text Files with Get-Content

The assignment covered reading text file contents.

**Example:**

```powershell
Get-Content example.txt
```

**Technical Explanation:**

`Get-Content` retrieves the content of a file and returns it to the PowerShell pipeline.

**Administrative Applications:**

- Reading log files.
- Inspecting configuration files.
- Processing text-based reports.
- Reviewing diagnostic information.

### 5.7 Writing Text Files with Set-Content

The assignment also covered modifying file content.

**Example:**

```powershell
Set-Content -Path example.txt -Value "PowerShell Administration Lab"
```

**Technical Explanation:**

`Set-Content` writes the specified value to a file, replacing its existing content by default.

This is useful for basic file creation and content updates.

### 5.8 File Processing & Automation Concepts

PowerShell can combine cmdlets to automate repetitive file operations.

The training introduced foundational workflows involving:

- Collecting system information.
- Exporting structured data.
- Transforming file formats.
- Reading existing file content.
- Writing updated content.
- Combining commands through pipelines.

### Technical Outcome

Explored PowerShell-based process data export, CSV-to-JSON conversion, and text file processing.

These exercises introduced structured data handling techniques used in system administration and automation.

---

## 🛠️ 6. PowerShell Command Reference

| Cmdlet / Operator | Purpose | Coverage |
|---|---|---|
| `Get-Process` | Retrieve running processes | Assignment |
| `Get-Service` | Retrieve Windows services | Assignment |
| `Where-Object` | Filter pipeline objects | Assignment |
| `\|` | Pass objects through a pipeline | Assignment |
| `Get-Alias` | Inspect existing aliases | Related reference |
| `Set-Alias` | Define a command alias | Related reference |
| `Export-Csv` | Export objects to CSV | Assignment |
| `Import-Csv` | Import CSV records as objects | Conversion example |
| `ConvertTo-Json` | Convert objects to JSON | Conversion example |
| `Get-Content` | Read file content | Assignment |
| `Set-Content` | Write file content | Assignment |

---

## ✅ 7. Verification & Technical Results

| Assignment | Technical Activity | Supporting Evidence |
|---|---|---|
| Basic Cmdlets | Process and service monitoring | Cmdlet execution screenshot |
| Pipelines | Process filtering with `Where-Object` | Pipeline screenshot |
| Aliases | Exploring and creating command aliases | Alias screenshot |
| CSV Export | Exporting process information | CSV export screenshot |
| JSON Conversion | CSV-to-JSON transformation | Assignment documentation |
| Text Processing | Reading and writing file content | Assignment documentation |

The screenshots document selected command-line exercises. Other activities are described in the original assignment report without separate screenshot evidence.

---

## 📸 8. Supporting Evidence

### 8.1 Get-Process & Get-Service

PowerShell cmdlet execution for inspecting running processes and Windows services.

![Get-Process and Get-Service](Screenshots/Get-Process-and-Get-Service.png)

**Activities Demonstrated:**

- Process monitoring using `Get-Process`.
- Service monitoring using `Get-Service`.
- Basic PowerShell command execution.

### 8.2 Process Filtering Pipeline

Pipeline-based process filtering using `Where-Object`.

![Process Filtering Pipeline](Screenshots/Process-Filtering-Pipeline.png)

**Activities Demonstrated:**

- Passing objects through PowerShell pipelines.
- Filtering process information.
- Inspecting accumulated process CPU time.

### 8.3 Aliases & Custom Alias Creation

PowerShell alias exploration and custom alias configuration.

![Aliases and Custom Alias Creation](Screenshots/Aliases-and-Custom-Alias.png)

**Activities Demonstrated:**

- Viewing built-in aliases.
- Creating custom aliases.
- Simplifying interactive commands.

### 8.4 CSV Export

Process information exported into CSV format.

![CSV Export](Screenshots/CSV-Export.png)

**Activities Demonstrated:**

- Exporting process information.
- Generating structured data files.
- Collecting information for reporting.

---

## 🧠 9. Key Learning Outcomes

- Practiced fundamental PowerShell cmdlets.
- Retrieved running process information.
- Inspected Windows service status.
- Understood object-based pipeline processing.
- Used `Where-Object` for conditional filtering.
- Explored built-in and custom command aliases.
- Exported process data to CSV.
- Studied CSV-to-JSON conversion.
- Practiced text file reading and modification.
- Understood structured data processing workflows.
- Developed foundational Windows administration and automation knowledge.

---

## 🚀 10. Lab Summary

This PowerShell administration capstone covered command-line administration, process and service monitoring, pipelines, aliases, CSV export, JSON conversion, and file manipulation.

The assignments introduced PowerShell as a practical tool for interacting with Windows system information and automating repetitive administrative operations.

The documented exercises and supporting screenshots demonstrate foundational PowerShell knowledge developed during **Cognizant CIS Multicloud technical training**.

These skills provide a foundation for further learning in **Windows Server administration, cloud infrastructure, infrastructure automation, and DevOps engineering**.
