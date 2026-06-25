
---

# Exacoola Transfer API Example 🚀

Create and manage automated file transfers using the Exacoola API.

This repository provides examples for creating transfer tasks through the Exacoola Transfer API.

With the Transfer API, you can configure file transfers between registered devices with flexible options:

* Source and target devices
* File selection rules
* Transfer options
* Execution schedules
* Repeated transfers
* Synchronization transfers

Build your own automated file transfer workflow with Exacoola.

---

## What is Transfer API? 📦

The Exacoola Transfer API allows you to create and manage file transfer jobs between devices registered in your workspace.

A transfer defines:

* Where files are collected from
* Where files are delivered
* Which files should be transferred
* When the transfer should run
* How the transfer should be executed

After creating a transfer, Exacoola manages the transfer process based on your configuration.

---

## Transfer Structure 🔄

A transfer consists of three main components:

```
Source Device
      ↓
Transfer Configuration
      ↓
Target Device
```

You can define source conditions, target options, and execution schedules through API requests.

---

## Source Configuration 📥

Configure the source device and files to transfer.

### Supported Options

* Source device ID
* Source path
* File extension filtering
* File size conditions

  * Minimum file size
  * Maximum file size
* Filename filtering

  * Include specific text in filename

### Example

```
{
  "sourceDeviceId": "device-001",
  "sourcePath": "/data/source",
  "sourceOptions": {
    "extensions": [
      "jpg",
      "png"
    ],
    "minSize": 1024,
    "maxSize": 10485760,
    "fileNameContains": "report"
  }
}
```

---

## Target Configuration 📤

Configure the destination device and storage path.

### Supported Options

* Target device ID
* Target path
* Duplicate file handling
* Automatic sub-path creation

### Example

```
{
  "targetDeviceId": "device-002",
  "targetPath": "/data/backup",
  "targetOptions": {
    "duplicateHandling": "overwrite",
    "createSubPath": true
  }
}
```

---

## Transfer Execution ⚡

You can control when transfers are executed.

### Immediate Transfer

Start the transfer immediately after creation.

```
Create Transfer
        ↓
Execute Transfer
```

---

### Scheduled Transfer

Run transfers automatically based on a schedule.

Supported schedules:

* Every hour
* Daily at a specific time
* Weekly at a specific time
* Monthly at a specific time

Examples:

```
Every hour

Every day at 02:00 AM

Every Monday at 09:00 AM

Every month on the 1st day
```

---

## Transfer Types 🔄

### Repeated Transfer

Automatically executes transfers based on the configured schedule.

Useful for:

* Periodic backups
* Regular file delivery
* Automated data collection

---

### Synchronization Transfer

Keeps source and target data synchronized.

Useful for:

* Data mirroring
* Continuous file synchronization
* Device data management

---

## API Flow 🔧

The typical workflow:

```
1. Create Workspace
          ↓
2. Register Devices
          ↓
3. Generate API Key
          ↓
4. Create Transfer
          ↓
5. Monitor Transfer Status
```

---

## Getting Started 🏁

To create your first transfer:

1. Create an Exacoola workspace
2. Register source and target devices
3. Generate an API key
4. Configure transfer options
5. Send a transfer creation request
6. Monitor the transfer status

---

## Documentation 📚

Learn more about Exacoola:

* Developer Guide
* API Reference

---

