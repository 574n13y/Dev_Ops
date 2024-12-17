# Day 41

1. **Linux**: Use kill to terminate processes and explain process signals.
   * The `kill` command in Linux is used to send signals to processes, allowing you to manage and terminate them.

   #### **Syntax:**
      ```bash
      kill [signal] <PID>
      ```

   - **`<PID>`**: Process ID of the target process.
   - **`[signal]`**: The signal to send (default is `SIGTERM` - signal 15).

   #### **Common Signals:**
    | Signal Name | Number | Description                         |
    |-------------|--------|-------------------------------------|
    | `SIGTERM`   | 15     | Graceful termination of a process.  |
    | `SIGKILL`   | 9      | Forcefully kills the process.       |
    | `SIGHUP`    | 1      | Reloads the process configuration.  |
    | `SIGSTOP`   | 19     | Pauses (stops) the process.         |
    | `SIGCONT`   | 18     | Resumes a paused process.           |

   #### **Examples:**
   1. **List processes and find the PID:**
      ```bash
      ps aux | grep <process_name>
      ```

   2. **Gracefully terminate a process:**
      ```bash
      kill -15 <PID>
      ```

   3. **Forcefully kill a process:**
      ```bash
      kill -9 <PID>
      ```

   4. **Kill all instances of a process:**
      ```bash
      pkill <process_name>
      ```

   5. **Send a stop signal to a process:**
      ```bash
      kill -19 <PID>
      ```


2. **Networking**: Describe NAT and its purpose in networking.
   * 
3. **Cloud Computing**: What is AWS CloudTrail, and how is it used?
   * 
4. **DevOps**: Describe the role of artifact repositories in CI/CD.
   * 
5. **Tools & Technology**: Install and configure Nexus or Artifactory as an artifact repository.
   * 
6. **Scenario**: Your CI/CD pipeline needs a place to store build artifacts. What would you recommend?
   * 
