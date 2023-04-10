<h1 align="center">
  Taskbook
</h1>

## Description

By utilizing a simple and minimal usage syntax, that requires a flat learning curve, taskbook enables you to effectively manage your tasks and notes across multiple boards from within your terminal. All data are written atomically to the storage in order to prevent corruptions, and are never shared with anyone or anything. Deleted items are automatically archived and can be inspected or restored at any moment.

## Install

### Yarn

```bash
yarn global add taskbook
```

### NPM

```bash
npm install --global taskbook
```

### Snapcraft

```bash
snap install taskbook
snap alias taskbook tb # set alias
```

**Note:** Due to the snap's strictly confined nature, both the storage & configuration files will be saved under the [`$SNAP_USER_DATA`](https://docs.snapcraft.io/reference/env) environment variable instead of the generic `$HOME` one.

## Problem Statement

Implement a new feature that allows users to set priority levels for tasks.  

Taskbook currently allows users to create and manage tasks, notes, and boards in a command-line interface. Your task is to enhance Taskbook by adding a new feature that enables users to assign priority levels (low, medium, or high) to tasks and sort them accordingly.  

To complete this challenge, you should: 

1. Analyze the codebase to understand its structure and how tasks are currently managed.  

2. Implement a new feature that allows users to assign priority levels (low, medium, or high) when creating or updating tasks.  

3. Modify the existing sorting logic to display tasks in order of their priority levels.  

4. Update the documentation and help messages within Taskbook to include information about the new priority feature.  

Test your changes thoroughly to ensure they work correctly without introducing any bugs or breaking existing functionality.

## Solution

The solution would involve analyzing the Taskbook codebase, understanding its structure and task management logic, and implementing the new priority feature.   

For example:    

1. Modify src/taskbook.js file's add method to accept an additional parameter for priority level:   

add(data, type = 'task', priority = 'medium') {
// ... rest of method
}  

2. Update the _validateInput method in src/taskmanager.js file to validate input for the new priority levels:  

_validateInput(data, type) { 
// ... existing validation logic  
if (type === 'priority' && !['low', 'medium',
'high'].includes(data)) { throw new Error('Invalid priority level');
} 
}    

3. Modify the task creation logic in src/taskmanager.js to store the priority level for each task and update the sorting logic to consider priority levels.     

4. Update documentation, help messages, and command-line options to include information about the new priority feature.     

After implementing the new feature and thoroughly testing the changes, you can create a pull request to the repository with your modifications and updated documentation.
    
